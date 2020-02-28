---
title: Qubits ile çalışma
description: Qubit ayırmayı öğrenin, bunları işlemler ve işlevlerde kullanın ve sonuçları ölçün.
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 1aa2432996dda61d099e3b5bb4db78379ce43d97
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907656"
---
# <a name="working-with-qubits"></a>Qubits ile çalışma

Artık, Q # dilinin çeşitli farklı parçalarını gördüğünüze göre, bunun kalın olmasını sağlamamıza ve qubits 'in kendisini nasıl kullanacağınızı görelim.

## <a name="allocating-qubits"></a>Qubit ayırma

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

## <a name="intrinsic-operations"></a>İç Işlemler

Ayrıldıktan sonra, bir qubit daha sonra işlevlere ve işlemlere geçirilebilirler.
Bazı bir deyişle, bu, bir Q # programının bir qubit ile yapamalarıdır, ancak gerçekleştirilebilecek eylemler tüm işlemler olarak tanımlanır.
Bu işlemleri, [Iç işlemler ve işlevlerde](xref:microsoft.quantum.libraries.standard.prelude)daha ayrıntılı bir şekilde görebiliyoruz, ancak şimdilik, qubits ile etkileşim kurmak için kullanılabilecek birkaç faydalı işlemden bahsedin.

İlk olarak, tek qubit Pauli Operators $X $, $Y $ ve $Z $, her birinin türü `Y`olan iç işlemler `X`, `Z`ve `(Qubit => Unit is Adj + Ctl)`tarafından Q # içinde temsil edilir.
[Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude)bölümünde açıklandığı gibi, $X $ ve bu nedenle `X` bir bit çevirme işlemi olarak veya ağ geçidi olmayan bir işlem olarak düşünebiliriz.
`X` işlemi, bazı klasik bit dizeler için $ \ket{s_0 s_1 \noktalara s_n} $ biçimindeki durumları hazırlanmamızı sağlar $s $:

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

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> Daha sonra, bu işlemi yazmak için el ile akış denetimi gerektirmeyen daha kompakt yollar görüyoruz.

Ayrıca, iç işlem{0} Q # içinde temsil edilen Hadamard Transform{1}$ ' i kullanarak $ \ket{+} = \left (\demet{0} + \tus{1}\right)/\sqrt{2}$ ve $ \tus{-} = \left (\ket{2}-\tus$H \right)/\sqrt `H : (Qubit => Unit is Adj + Ctl)`$ gibi durumları hazırlayabiliriz:

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

## <a name="measurements"></a>Ölçümler

Yerleşik bir içsel Unitary işlemi olan `Measure` işlemini kullanarak, `Qubit` türünde bir nesneden klasik bilgileri ayıklayabilir ve bir klasik değeri, ayrılmış bir tür `Result`olan sonuç olarak atayabiliriz ve bu da sonucun artık hisse amadığı anlamına gelir.
`Measure` girişi, Bloch Sphere üzerinde `Pauli` (örneğin `PauliX`) ve `Qubit`türünde bir değer ile temsil edilen Pauli eksenindedir.

Basit bir örnek, $ \demet{0}$ durumunda bir qubit ayıran aşağıdaki işlemdir ve sonra bu `H` bir Hadamard işlemi uygular ve sonucu `PauliZ` temelinde ölçer.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
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

Aşağıdaki işlem tarafından biraz daha karmaşık bir örnek verilmiştir ve bu `Qubit[]` tür bir kayıttaki tüm qubits 'ler belirtilen bir Pauli tabanında ölçülerek sıfır durumunda ise ve bu, aksi halde `false` döndüren `true` Boole değeri döndürür.

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

Q # dili, mebitleri ölçmeye yönelik sonuçlara bağlı olarak klasik denetim akışına izin verir.
Bu özellik sırasıyla, birimlere uygulama için hesaplama maliyetini azaltabilecekleri güçlü dayalı araçları uygulamaya olanak tanıyor.
Örnek olarak, Q # içinde *Yinele-başarılı* (ru) desenleri uygulamak çok kolaydır.
Bu RUS desenleri, temel kapıların bakımından *beklenen* düşük maliyetli dayalı programlarıdır, ancak gerçek maliyetten gerçek bir çalıştırmaya ve çeşitli olası branchlerin gerçek bir aramasına bağlı olarak değişir.

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

`statementBlock1` ve `statementBlock2` sıfır veya daha fazla Q # deyimi ve `Bool`türünde bir değer değerlendirilen herhangi bir geçerli ifade `expression`.
Tipik bir kullanım durumunda, aşağıdaki Q # işlemi Bloch Sphere üzerinde $ (I + 2i Z)/\sqrt{5}$ bir ırrational Axis etrafında bir döndürme uygular. Bu, bilinen bir RUS kalıbı kullanılarak gerçekleştirilir:

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

Bu örnek, tüm yineleme-sonu-düzeltme döngüsü kapsamında olan ve düzeltme adımında yüklenmeden önce başlatılan bir kesilebilir değişken `finished` kullanımını gösterir.

Son olarak, $ \ket{+} $ durumundan başlayarak bir hisse durumu $ \frac{1}{\sqrt{3}} \left (\sqrt{2}\tus{0}+ \tus{1}\right) $ ' ı hazırlamak için bir RUS deseninin örneğini gösteririz.
Ayrıca bkz. [Standart kitaplıkla birlikte sunulan birim testi örneği](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Bu işlemde gösterilen önemli programlı özellikler, bir döngünün daha karmaşık `fixup` bir parçasıdır. Bu, hisse kullanımı ve programda belirtilen belirli noktalarda hisse TI ölçme olasılığını belirlemek için `AssertProb` deyimlerinin kullanılmasını içerir.
Ayrıca, [`Assert`](xref:microsoft.quantum.intrinsic.assert) ve [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) işlemleri hakkında daha fazla bilgi için bkz. [test ve hata ayıklama](xref:microsoft.quantum.techniques.testing-and-debugging) .
