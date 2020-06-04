---
title: Kubitlerle çalışma
description: Fill açıklaması
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 0deb0729a88c49798f32a22a943b935d383c570b
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327552"
---
# <a name="working-with-qubits"></a>Kubitlerle çalışma

Artık, Q # dilinin çeşitli farklı parçalarını gördüğünüze göre, bunun kalın olmasını sağlamamıza ve qubits 'in kendisini nasıl kullanacağınızı görelim.

Bir işlevin gövdesinde bu deyimlerden hiçbirine izin verilmediğini unutmayın.
Bunlar yalnızca işlemler içinde geçerlidir.

## <a name="allocating-qubits"></a>Qubit ayırma

### <a name="clean-qubits"></a>Qubit Temizleme

`using`İfade, bir ifade bloğu sırasında kullanılmak üzere yeni qubit *ayırmak* için kullanılır.

İfade, anahtar sözcüğünden `using` , ardından bir açık parantez `(` , bir bağlama, bir kapatma parantezi `)` ve qubits 'in kullanılabileceği deyimin bloğunu içerir.
Bağlama deyimlerle aynı düzeni izler `let` : tek bir sembol veya sembol kümesi, ardından eşittir işareti `=` ve tek bir değer ya da eşleşen *Başlatıcı*grubu.

Başlatıcılar tek bir qubit için, `Qubit()` veya bir qubit dizisi olarak belirtilir, `Qubit[n]` burada `n` bir `Int` ifadedir.
Örneğin,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

Bu şekilde ayrılan her türlü qubit, {0} Yukarıdaki örnekte $ \tus$ State; üzerinde başlatılır. bu nedenle, bu `register` durumda $ \ket {00000} = \ket {0} \otimes {0} \gre\otimes \cnoktalar \otimes \ment {0} $ şeklindedir.
`using`Bloğun sonunda, bu blok tarafından ayrılan tüm qubitleri hemen serbest bırakılır ve daha fazla kullanılamaz.

> [!WARNING]
> Hedef makineler, bu qubits 'in {0} yeniden kullanılabilmesi ve `using` ayırma için diğer bloklara sunulabilmeleri için $ \ket $ durumunda olmasını bekler.
> Mümkün olduğunda, tüm ayrılmış qubitleri $ \ket $ ' e döndürmek için Unitary işlemlerini kullanın {0} .
> Gerekirse, @"microsoft.quantum.intrinsic.reset" işlem bunun yerine bir qubit ölçmek için ve bu ölçüm sonucunu kullanarak ölçülen qubit $ \ket $ ' e döndürüldüğünden emin olmak için kullanılabilir {0} . Bu tür bir ölçü, kalan qubits ile herhangi bir entanglement 'i yok eder ve bu sayede hesaplamayı etkileyebilir.


### <a name="borrowed-qubits"></a>Ödünç alınan qubits

`borrowing`Bu ifade, qubits 'in belirli bir durumda olması gerekmeyen geçici kullanım için kullanılabilir olması için kullanılır.

Ödünç alma mekanizması, bir hesaplama sırasında karalama alanı olarak kullanılabilecek qubits ayrılmasına izin verir.
Bu qubits genellikle temiz bir durumda değildir, yani $ \ket $ gibi bilinen bir durumda başlatılmazlar {0} .
Bunlar genellikle "kirli" qubit olarak adlandırılır, çünkü durumları bilinmez ve hatta hisse bilgisayar belleğinin diğer bölümleriyle eşit bir şekilde de olabilir.

Bağlama, bir deyimdeki ile aynı model ve kurallara uyar `using` .
Örneğin,
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
Ödünç alınan qubits, bilinmeyen bir durumda ve bildiri bloğunun sonundaki kapsam dışına çıkar.
Ödünç alma, qubits 'i ödünç aldıkları aynı durumda bırakır, yani deyimin başındaki ve sonundaki durumları aynı olmalıdır. bu durum, ifade bloğunun başındaki ve sonundaki durumunun aynı olması beklenir.
Özellikle bu durum klasik bir durum değildir; çoğu durumda, ödünç alınan kapsamlar ölçüm içermemelidir. 

Qubits 'i ödünç alırken, sistem önce kullanımda olan ancak deyimin gövdesi sırasında erişilemeyen qubits 'lerden gelen isteği doldurmaya çalışacaktır `borrowing` .
Bu tür qubit yoksa, isteği tamamlayacak yeni qubit ayırabilirsiniz.


Kirli qubits 'in bilinen kullanım durumları arasında, yalnızca çok az sayıda qubit ve incrementers uygulaması gerektiren çok kontrollü CNOT kapıları olan uygulamalardır.
[Örnek olarak](#borrowing-qubits-example) , soru-cevap veren bir algoritma için soru-cevap, düzenleme ve Toffoli tabanlı modüler çarpma (haner, Roetteler ve svore 2017) [*ile 2n + 2 qubit kullanma*](https://arxiv.org/abs/1611.07995) hakkında


## <a name="intrinsic-operations"></a>İç Işlemler

Ayrıldıktan sonra, bir qubit daha sonra işlevlere ve işlemlere geçirilebilirler.
Bazı bir deyişle, bu, bir Q # programının bir qubit ile yapamalarıdır, ancak gerçekleştirilebilecek eylemler tüm işlemler olarak tanımlanır.
Bu işlemleri, [Iç işlemler ve işlevlerde](xref:microsoft.quantum.libraries.standard.prelude)daha ayrıntılı bir şekilde görebiliyoruz, ancak şimdilik, qubits ile etkileşim kurmak için kullanılabilecek birkaç faydalı işlemden bahsedin.

İlk olarak, tek qubit Pauli Operators $X $, $Y $ ve $Z $, `X` `Y` her birinin türüne sahip olan iç işlemler, ve, ve `Z` her biri için Q # içinde temsil edilir `(Qubit => Unit is Adj + Ctl)` .
[Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude)bölümünde açıklandığı gibi, $X $ ve bu nedenle `X` bir bit çevirme işlemi olarak veya ağ geçidi değil, bu şekilde düşünebiliriz.
`X`İşlem, bazı klasik bit dizeler için $ \ket{s_0 s_1 \noktalara S_N} $ biçimindeki durumları hazırlamanızı sağlar $s $:

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

Ayrıca, {0} {1} {2} {-} {0} {1} {2} iç Işlem tarafından Q # içinde temsil edilen Hadamard Transform $H $ ' i kullanarak $ \ket{+} = \left (\ket + \ket \ right)/\sqrt $ ve $ \ket = \left (\tus-\ket \ right)/\sqrt $ gibi durumları hazırlayabiliriz `H : (Qubit => Unit is Adj + Ctl)` :

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

`Measure`Yerleşik bir iç sıra olmayan işlem olan işlemi kullanarak, türü bir nesneden klasik bilgileri ayıklayabilir `Qubit` ve sonuç olarak bir klasik değer atayabiliriz ve `Result` Bu da sonucun artık hisse amamış olmadığını gösterir.
Girişi, `Measure` Bloch Sphere üzerinde, türü `Pauli` (örneğin, `PauliX` ) ve türünde bir değer ile temsil edilen bir Pauli ekseni `Qubit` .

Basit bir örnek, $ \ket $ durumunda bir qubit ayıran aşağıdaki işlemdir {0} , ardından buna bir Hadamard işlemi uygular `H` ve sonucu `PauliZ` temelde ölçer.

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

Aşağıdaki işlem tarafından biraz daha karmaşık bir örnek verilmiştir `true` ve bu tür bir kayıttaki tüm qubits `Qubit[]` 'ler, belirtilen bir Pauli tabanında ölçülerek sıfır durumunda ise ve aksi takdirde bu değer geri döndüğünde Boolean değeri döndürür `false` .

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

## <a name="borrowing-qubits-example"></a>Ödünç alma qubits örneği

Canon, `borrowing` anahtar sözcüğünü kullanan örnekler, örneğin, `MultiControlledXBorrow` aşağıda tanımlanan işlev.
`controls`Bir işleme eklenmesi gereken denetimi qubits 'e işaret ederseniz `X` , `Length(controls)-2` Bu uygulama tarafından birçok kirli ve daha fazla Las 'nin bir bütün olarak eklenmesi gerekir.

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

`With`Combinator---'ın, adjoint 'i destekleyen işlemler için geçerli olan (Bu örnekte,---) kapsamlı olarak kullanılması gerektiğini unutmayın `WithA` .
Denetimi yalnızca iç işleme yayar içeren yapılara denetim eklemek için bu iyi bir programlama stilidir `With` .
Ayrıca, bu işlemin yanı sıra, işlem `body` `controlled` gövdesinin bir uygulamasının bir deyime yeniden değil, açıkça sağlandığını unutmayın `controlled auto` .
Bunun nedeni, bağlantı hattı yapısından, her bir ve içindeki her bir kapıya denetim eklemeye kıyasla yararlı olan daha fazla denetimi nasıl kolayca ekleyebiliyoruz `body` . 

Bu kodu başka bir Canon işleviyle karşılaştırmak `MultiControlledXClean` `X` , ancak mekanizmayı kullanarak birkaç temiz qubit kullanan, çarpma denetimli bir işlem uygulama amacını elde eder `using` . 

## <a name="next-steps"></a>Sonraki adımlar

Q # içindeki [Denetim akışı](xref:microsoft.quantum.guide.controlflow) hakkında bilgi edinin.