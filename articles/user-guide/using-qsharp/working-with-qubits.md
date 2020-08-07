---
title: Kubitlerle çalışma
description: Fill açıklaması
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6808a852ee0de7d3a38ea44e9637eeaa6bea382a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867871"
---
# <a name="working-with-qubits"></a>Kubitlerle çalışma

Qubits, hisse bilgi işlem ortamında temel bilgilerin temel nesnesidir. Qubits 'e genel bir bakış için bkz. [hisse parlaklığını anlama](xref:microsoft.quantum.overview.understanding)ve matematiksel gösterimlerine daha ayrıntılı bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit). 

Bu makalede, bir programda qubits 'in nasıl kullanılacağı ve bunlarla nasıl çalıştığı açıklanır Q# . 

> [!IMPORTANT]
>Bu makalede ele alınan deyimlerden hiçbiri bir işlevin gövdesinde geçerli değildir. Bunlar yalnızca işlemler içinde geçerlidir.

## <a name="allocating-qubits"></a>Qubit ayırma

Fiziksel qugeler, bir hisse bilgisayarında değerli bir kaynak olduğundan, derleyicinin işinin bir parçası mümkün olduğunca verimli şekilde kullanıldıklarından emin olmak.
Bu nedenle, Q# belirli bir ekstre bloğunda kullanmak üzere qubit *ayırmak* için söylemeniz gerekir.
Qubits 'i tek bir qubit ya da *kayıt*olarak bilinen bir qubits dizisi olarak ayırabilirsiniz. 

### <a name="clean-qubits"></a>Qubit Temizleme

Bildirim `using` bloğu sırasında kullanılmak üzere yeni qubit ayırmak için ifadesini kullanın.

İfade, anahtar sözcüğünden `using` , ardından parantez içine alınmış bir bağlama `( )` ve qubits 'in kullanılabildiği ifade bloğunun bir öğesinden oluşur.
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

Bu şekilde ayrılan her türlü qubit $ \ket {0} $ durumunda başlatılır. Bu nedenle, önceki örnekte, `auxiliary` $ \ket $ durumunda tek bir qubit bulunur {0} ve `register` beş-qubit State $ {00000} \tus= \ket {0} \otimes \ayraç {0} \otimes \cnoktalar \otimes \ket $ ' de bulunur {0} .
`using`Bloğun sonunda, bu blok tarafından ayrılan tüm qubitleri hemen serbest bırakılır ve daha fazla kullanılamaz.

> [!WARNING]
> Hedef makineler serbest bırakılmış qugeler kullanabilir ve bunları `using` ayırma için diğer bloklara sunabilir. Bu nedenle, hedef makine, bu qubits 'in {0} ayırmayı kaldırma işleminden hemen önce $ \ket $ durumunda olmasını bekler.
> Mümkün olduğunda, tüm ayrılmış qubitleri $ \ket $ ' e döndürmek için Unitary işlemlerini kullanın {0} .
> Gerekiyorsa, @"microsoft.quantum.intrinsic.reset" {0} bunu ölçerek ve sonuca göre koşullu bir işlem gerçekleştirerek, qubit ile $ \ket $ ' i döndüren işlemi kullanabilirsiniz. Bu tür bir ölçü, kalan qubits ile herhangi bir entanglement 'i yok eder ve bu sayede hesaplamayı etkileyebilir.


### <a name="borrowed-qubits"></a>Ödünç alınan qubits

`borrowing`Belirli bir durumda olması gerekmeyen, geçici kullanım için qubit ayırmak üzere ifadesini kullanın.

Hesaplama sırasında ödünç alınan qubits 'i boş alan olarak kullanabilirsiniz.
Bu qubits genellikle temiz bir durumda değildir, diğer bir deyişle, $ \ket $ gibi bilinen bir durumda başlatılmamalıdır {0} .
Bunlar genellikle "kirli" qubit olarak adlandırılır, çünkü durumları bilinmez ve hatta hisse bilgisayar belleğinin diğer bölümleriyle eşit bir şekilde de olabilir.

Bağlama, ifadesiyle aynı model ve kurallara uyar `using` .
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
Ödünç alma, qubits 'i ödünç aldıkları durum ile aynı durumda bırakarak, diğer bir deyişle, ekstre bloğunun başındaki ve sonundaki durum aynı olmalıdır.
Bu durum klasik bir durum olmadığı için çoğu durumda, ödünç alınan kapsamlar ölçüm içermemelidir. 

Qubits 'i ödünç alırken, sistem ilk olarak isteği kullanımda olan ancak deyimin gövdesinde erişilmeyen qubits 'lerden doldurmaya çalışır `borrowing` .
Bu tür qubit yoksa, isteği tamamlaması için yeni qubit ayırır.

Kirli qubits 'in bilinen kullanım durumları arasında, yalnızca çok az sayıda qubit ve incrementers uygulaması gerektiren çok kontrollü CNOT kapıları olan uygulamalardır.
İçindeki kullanımları hakkında bir örnek için Q# , bu makaledeki [Qubitleri örnek olarak ödünç](#borrowing-qubits-example) alma veya düzenleme kağıt, [*Toffoli tabanlı modüler çarpma*](https://arxiv.org/abs/1611.07995) (haner, Roetteler ve svore 2017) ile birlikte, ödünç alınan qubits kullanan bir algoritma için bkz. 2.

## <a name="intrinsic-operations"></a>İç Işlemler

Ayrıldıktan sonra işlevlere ve işlemlere bir qubit geçirebilirsiniz.
Bazı bir deyişle, bir Q# programın bir qubit ile yapamamaları, ancak gerçekleştirilebilecek eylemler tüm işlemler olarak tanımlanmıştır.

Bu makalede, Q# qubits ile etkileşim kurmak için kullanabileceğiniz birkaç faydalı işlem ele alınmaktadır.
Bunlar ve diğerleri hakkında daha fazla ayrıntı için bkz. [Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude). 

İlk olarak, tek qubit Pauli Operators $X $, $Y $ ve $Z $, Q# [`X`](xref:microsoft.quantum.intrinsic.x) [`Y`](xref:microsoft.quantum.intrinsic.y) [`Z`](xref:microsoft.quantum.intrinsic.z) her birinin türüne sahip olan iç işlemler, ve, ile temsil edilir `(Qubit => Unit is Adj + Ctl)` .

[Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude)bölümünde açıklandığı gibi, $X $ ve bu nedenle, `X` bir bit çevirme işlemi veya ağ geçidi değil olarak düşünün.
`X`Bazı klasik bit dizeler için $ \ket{s_0 s_1 \noktalara S_N} $ biçimindeki durumları hazırlamak için bu işlemi kullanabilirsiniz $s $:

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
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> Daha sonra, bu işlemi yazmak için el ile denetim akışı gerektirmeyen daha kompakt yollar görürsünüz.

Ayrıca, $ \ket{+} = \left (\ket {0} + \ket {1} \ right)/\sqrt {2} $ ve $ \ket {-} = \left (\tus- {0} \ket {1} \ right)/\Sqrt $ gibi durumları, {2} Hadamard Transform $H $ kullanarak da hazırlayabilirsiniz. Q# iç işlem tarafından temsil edilen [`H`](xref:microsoft.quantum.intrinsic.h) (qubit => Unit, sıfatı + CTL) '):

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a>Ölçümler

Tek tek qubit ölçümleri, her biri [Bloch Sphere](xref:microsoft.quantum.glossary#bloch-sphere)üzerinde bir Pauli ekseni tarafından temsil edilen farklı tabanlarda gerçekleştirilebilir.
*Hesaplama temeli* temel anlamına gelir `PauliZ` ve ölçüm için en yaygın olarak kullanılan temeldir.

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>Temelde tek bir qubit ölçme `PauliZ`

[`M`](xref:microsoft.quantum.intrinsic.m)Temelinde tek bir qubit ölçmek `PauliZ` ve sonuca bir klasik değer atamak için yerleşik bir içsel Unitary işlemi olan işlemi kullanın.
`M`, `Result` yalnızca değer `Zero` `One` elde eden veya ölçülen durum $ \ket {0} $ veya $ \ket {1} $-sonucu yalnızca bir hisse

Basit bir örnek, $ \ket $ durumunda bir qubit ayıran aşağıdaki işlemdir {0} , ardından buna bir Hadamard işlemi uygular `H` ve sonucu `PauliZ` temelde ölçer.

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>Belirli tabanlarda bir veya daha fazla qubit ölçme

Belirli tabanlarda bir veya daha fazla qubit dizisini ölçmek için, [`Measure`](xref:microsoft.quantum.intrinsic.measure) işlemini kullanabilirsiniz.

İçin girdiler, `Measure` türlerin bir dizisidir `Pauli` (örneğin, `[PauliX, PauliZ, PauliZ]` ) ve bir qubit dizisidir.

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

Bu örneğin `Measure` her seferinde yalnızca tek bir qubits üzerinde devam ettiğinden, ancak işlem birden çok qubit üzerinde birlikte bulunan ölçümlere genişletilebilir.

## <a name="borrowing-qubits-example"></a>Ödünç alma qubits örneği

`borrowing`Aşağıdaki işlev gibi, Canon anahtar sözcüğünü kullanan örnekler vardır `MultiControlledXBorrow` . `controls`Denetimi bir işleme eklemek için denetim qubits 'e işaret ederseniz `X` , bu uygulama tarafından eklenen kirli [ancillas](xref:microsoft.quantum.glossary#ancilla) bir ve daha fazla değer vardır `Length(controls)-2` .

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

Bu örnekte,, `With` Örneğin, adjoint 'i destekleyen işlemler için geçerli olan Combinator 'ın kapsamlı kullanımını kullandığına unutmayın `WithA` .
Denetimi yalnızca iç işleme yayar içeren yapılara denetim eklemek için bu iyi bir programlama stilidir `With` .
Ayrıca, işlemin yanı sıra, `body` `controlled` bir ifadeye daha sonra değil, işlemin gövde bir uygulamasının açıkça sağlandığını unutmayın `controlled auto` .
Bunun nedeni, devrenin yapısı nedeniyle, içindeki her bir kapıya denetim eklemeye kıyasla yararlı olan daha fazla denetim eklemek kolaydır `body` . 

Bu kodu başka bir Canon işleviyle karşılaştırmak `MultiControlledXClean` `X` , ancak mekanizmayı kullanarak birkaç temiz qubit kullanan, çarpma denetimli bir işlem uygulama amacını elde eder `using` . 

## <a name="next-steps"></a>Sonraki adımlar

İçindeki [Denetim akışı](xref:microsoft.quantum.guide.controlflow) hakkında bilgi edinin Q# .