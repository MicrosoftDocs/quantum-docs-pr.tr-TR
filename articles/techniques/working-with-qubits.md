---
title: Qubits ile çalışma | Microsoft Docs
description: Qubits ile çalışma
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: d1a8ccc9423a9a04e12bc98e3783790232b2f5d8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183480"
---
# <a name="working-with-qubits"></a>Qubits ile çalışma #

Artık, Q # dilinin çeşitli farklı parçalarını gördüğünüze göre, bunun kalın olmasını sağlamamıza ve qubits 'in kendisini nasıl kullanacağınızı görelim.

## <a name="allocating-qubits"></a>Qubit ayırma ##

İlk olarak, Q # ' da kullanabilmemiz için bir qubit elde etmek üzere `using` bloğu içinde qubit *ayırdık* :

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

Bu şekilde ayrılan her türlü qubit $ \ket{0}$ State; Yukarıdaki örnekte `register`, bu durumda $ \demet{00000} = \ayraç{0} \otimes \tus{0} \otimes \cnoktalar \otimes \tus{0}$ şeklindedir.
`using` bloğunun sonunda, bu blok tarafından ayrılan tüm qubitleri hemen serbest bırakılır ve daha fazla kullanılamaz.

> [!WARNING]
> Hedef makineler, daha sonra yeniden kullanılabilmesi ve ayrılmak üzere diğer `using` bloklara sunulabilmeleri için, qubits 'in $ \ket{0}$ durumunda olmasını bekler.
> Mümkün olduğunda, tüm ayrılmış qubitleri $ \ket{0}$ ' e döndürmek için Unitary işlemlerini kullanın.
> Gerekirse, @"microsoft.quantum.intrinsic.reset" işlemi bir qubit ' i ölçmek için ve bu ölçüm sonucunu kullanarak ölçülen qubitin $ \tus{0}$ ' e döndürüldüğünden emin olmak için kullanılabilir. Bu tür bir ölçü, kalan qubits ile herhangi bir entanglement 'i yok eder ve bu sayede hesaplamayı etkileyebilir. 

## <a name="intrinsic-operations"></a>İç Işlemler ##

Ayrıldıktan sonra, bir qubit daha sonra işlevlere ve işlemlere geçirilebilirler.
Bazı bir deyişle, bu, bir Q # programının bir qubit ile yapamalarıdır, ancak gerçekleştirilebilecek eylemler tüm işlemler olarak tanımlanır.
Bu işlemleri, [Iç işlemler ve işlevlerde](xref:microsoft.quantum.libraries.standard.prelude)daha ayrıntılı bir şekilde görebiliyoruz, ancak şimdilik, qubits ile etkileşim kurmak için kullanılabilecek birkaç faydalı işlemden bahsedin.

İlk olarak, tek qubit Pauli Operators $X $, $Y $ ve $Z $, her birinin türü `Y`olan iç işlemler `X`, `Z`ve `(Qubit => Unit is Adj + Ctl)`tarafından Q # içinde temsil edilir.
[Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude)bölümünde açıklandığı gibi, $X $ ve bu nedenle `X` bir bit çevirme işlemi olarak veya ağ geçidi olmayan bir işlem olarak düşünebiliriz.
Bu, bazı klasik bit dizeler için $ \ket{s_0 s_1 \noktalara S_N} $ biçimindeki durumları hazırlamanızı sağlar $s $:

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit 
is Adj + Ctl {

    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> Daha sonra, bu işlemi yazmak için el ile akış denetimi gerektirmeyen daha kompakt yollar görüyoruz.

Ayrıca, Hadamard dönüşümünü kullanarak $ \ket{+} = \left (\demet{0} + \tus{1}\right)/\sqrt{2}$ ve $ \tus{-} = \left (\demet{0}-\tus{1}\right)/\sqrt{2}$ gibi durumlar da hazırlayabiliriz $H $ `H : (Qubit => Unit is Adj + Ctl)`iç işlem tarafından Q # olarak temsil edilir:

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {

    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Ölçümler ##

Yerleşik bir yerleşik olmayan sıra dışı işlem olan `Measure` işlemini kullanarak, `Qubit` türünde bir nesneden klasik bilgiler ayıklayabilir ve bir klasik değeri, ayrılmış bir tür `Result`olan sonuç olarak atayabiliriz ve bu da sonucun Hayır olduğunu belirtir daha uzun bir hisse. `Measure` girişi, Bloch Sphere üzerinde `Pauli` türünde bir nesne (örneğin, `PauliX`) ve `Qubit`türünde bir nesne tarafından temsil edilen bir Pauli eksenindedir. 

Basit bir örnek, $ \demet{0}$ durumunda bir qubit oluşturan aşağıdaki işlemdir ve sonra bir Hadamard Gate ``H`` uygular ve sonra sonucu `PauliZ` temelinde ölçer. 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
        H(qubit); 
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator, 
        // we reset the qubit before releasing it. 
        if (result == One) { X(qubit); }   
        // Finally, we return the result of the measurement. 
        return result;
    }
}
```

Aşağıdaki işlem tarafından biraz daha karmaşık bir örnek verilmiştir `true` `Qubit[]` bir kayıttaki tüm qubits 'ler, belirtilen Pauli temelinde ölçülerek sıfır durumunda ise ve aksi takdirde `false`. 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

Q # dili, qubits 'in ölçüm sonuçlarında klasik denetim akışının bağımlılıklarına izin verir. Bu işlem, birimlere uygulama için hesaplama maliyetini azaltabilecekleri güçlü dayalı araçları uygulamayı sağlar. Örnek olarak, dayalı devreleri olan ve alt kapılar bakımından *beklenen* düşük maliyetli olan, ancak gerçek maliyetli gerçek bir çalıştırmaya ve gerçek maliyete bağlı olan devreleri olan, aynı şekilde uygulanması kolaydır. çeşitli olası branchler araya ekleme. 

Yinele-başarılı (RUS) desenleri kolaylaştırmak için, Q # yapıyı destekler
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
`statementBlock1` ve `statementBlock2` sıfır veya daha fazla Q # deyimi ve `Bool`türünde bir değer değerlendirilen herhangi bir geçerli ifade `expression`. Tipik bir kullanım durumunda aşağıdaki devre, Bloch Sphere üzerinde $ (I + 2i Z)/\sqrt{5}$ bir ırrational Axis etrafında bir döndürme uygular. Bu, bilinen bir RUS kalıbı kullanılarak gerçekleştirilir: 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

Bu örnek, tüm yineleme-sonu-düzeltme döngüsü kapsamında olan ve düzeltme adımında yüklenmeden önce başlatılan bir kesilebilir değişken `finished` kullanımını gösterir.

Son olarak, $ \ket{+} $ durumundan başlayarak bir hisse durumu $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\tus{0}+ \tus{1}\right) $ ' ı hazırlamak için bir RUS deseninin örneğini gösteririz. Ayrıca bkz. [Standart kitaplıkla birlikte sunulan birim testi örneği](https://github.com/Microsoft/Quantum/blob/master/Samples/src/UnitTesting/RepeatUntilSuccessCircuits.qs): 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
Bu işlemde gösterilen önemli bir programlı özellikler, bu işlemin bir parçası olan `fixup` daha karmaşık bir parçasıdır ve bu işlem, her bir belirli noktada hisse durumu ölçme olasılığını belirlemek için `AssertProb` deyimlerinin kullanımı programda. Ayrıca `Assert` ve `AssertProb` deyimleri hakkında daha fazla bilgi için bkz. [test ve hata ayıklama](xref:microsoft.quantum.techniques.testing-and-debugging) . 
