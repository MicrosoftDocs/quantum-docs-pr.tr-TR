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
# <a name="working-with-qubits"></a><span data-ttu-id="758a9-103">Kubitlerle çalışma</span><span class="sxs-lookup"><span data-stu-id="758a9-103">Working with qubits</span></span>

<span data-ttu-id="758a9-104">Artık, Q # dilinin çeşitli farklı parçalarını gördüğünüze göre, bunun kalın olmasını sağlamamıza ve qubits 'in kendisini nasıl kullanacağınızı görelim.</span><span class="sxs-lookup"><span data-stu-id="758a9-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

<span data-ttu-id="758a9-105">Bir işlevin gövdesinde bu deyimlerden hiçbirine izin verilmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="758a9-105">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="758a9-106">Bunlar yalnızca işlemler içinde geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="758a9-106">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="758a9-107">Qubit ayırma</span><span class="sxs-lookup"><span data-stu-id="758a9-107">Allocating Qubits</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="758a9-108">Qubit Temizleme</span><span class="sxs-lookup"><span data-stu-id="758a9-108">Clean qubits</span></span>

<span data-ttu-id="758a9-109">`using`İfade, bir ifade bloğu sırasında kullanılmak üzere yeni qubit *ayırmak* için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="758a9-109">The `using` statement is used to *allocate* new qubits for use during a statement block.</span></span>

<span data-ttu-id="758a9-110">İfade, anahtar sözcüğünden `using` , ardından bir açık parantez `(` , bir bağlama, bir kapatma parantezi `)` ve qubits 'in kullanılabileceği deyimin bloğunu içerir.</span><span class="sxs-lookup"><span data-stu-id="758a9-110">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="758a9-111">Bağlama deyimlerle aynı düzeni izler `let` : tek bir sembol veya sembol kümesi, ardından eşittir işareti `=` ve tek bir değer ya da eşleşen *Başlatıcı*grubu.</span><span class="sxs-lookup"><span data-stu-id="758a9-111">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="758a9-112">Başlatıcılar tek bir qubit için, `Qubit()` veya bir qubit dizisi olarak belirtilir, `Qubit[n]` burada `n` bir `Int` ifadedir.</span><span class="sxs-lookup"><span data-stu-id="758a9-112">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="758a9-113">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="758a9-113">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="758a9-114">Bu şekilde ayrılan her türlü qubit, {0} Yukarıdaki örnekte $ \tus$ State; üzerinde başlatılır. bu nedenle, bu `register` durumda $ \ket {00000} = \ket {0} \otimes {0} \gre\otimes \cnoktalar \otimes \ment {0} $ şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="758a9-114">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="758a9-115">`using`Bloğun sonunda, bu blok tarafından ayrılan tüm qubitleri hemen serbest bırakılır ve daha fazla kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="758a9-115">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="758a9-116">Hedef makineler, bu qubits 'in {0} yeniden kullanılabilmesi ve `using` ayırma için diğer bloklara sunulabilmeleri için $ \ket $ durumunda olmasını bekler.</span><span class="sxs-lookup"><span data-stu-id="758a9-116">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="758a9-117">Mümkün olduğunda, tüm ayrılmış qubitleri $ \ket $ ' e döndürmek için Unitary işlemlerini kullanın {0} .</span><span class="sxs-lookup"><span data-stu-id="758a9-117">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="758a9-118">Gerekirse, @"microsoft.quantum.intrinsic.reset" işlem bunun yerine bir qubit ölçmek için ve bu ölçüm sonucunu kullanarak ölçülen qubit $ \ket $ ' e döndürüldüğünden emin olmak için kullanılabilir {0} .</span><span class="sxs-lookup"><span data-stu-id="758a9-118">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="758a9-119">Bu tür bir ölçü, kalan qubits ile herhangi bir entanglement 'i yok eder ve bu sayede hesaplamayı etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="758a9-119">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="758a9-120">Ödünç alınan qubits</span><span class="sxs-lookup"><span data-stu-id="758a9-120">Borrowed Qubits</span></span>

<span data-ttu-id="758a9-121">`borrowing`Bu ifade, qubits 'in belirli bir durumda olması gerekmeyen geçici kullanım için kullanılabilir olması için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="758a9-121">The `borrowing` statement is used to make qubits available for temporary use, which do not need be in a specific state.</span></span>

<span data-ttu-id="758a9-122">Ödünç alma mekanizması, bir hesaplama sırasında karalama alanı olarak kullanılabilecek qubits ayrılmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="758a9-122">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span>
<span data-ttu-id="758a9-123">Bu qubits genellikle temiz bir durumda değildir, yani $ \ket $ gibi bilinen bir durumda başlatılmazlar {0} .</span><span class="sxs-lookup"><span data-stu-id="758a9-123">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="758a9-124">Bunlar genellikle "kirli" qubit olarak adlandırılır, çünkü durumları bilinmez ve hatta hisse bilgisayar belleğinin diğer bölümleriyle eşit bir şekilde de olabilir.</span><span class="sxs-lookup"><span data-stu-id="758a9-124">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="758a9-125">Bağlama, bir deyimdeki ile aynı model ve kurallara uyar `using` .</span><span class="sxs-lookup"><span data-stu-id="758a9-125">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>
<span data-ttu-id="758a9-126">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="758a9-126">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="758a9-127">Ödünç alınan qubits, bilinmeyen bir durumda ve bildiri bloğunun sonundaki kapsam dışına çıkar.</span><span class="sxs-lookup"><span data-stu-id="758a9-127">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="758a9-128">Ödünç alma, qubits 'i ödünç aldıkları aynı durumda bırakır, yani deyimin başındaki ve sonundaki durumları aynı olmalıdır. bu durum, ifade bloğunun başındaki ve sonundaki durumunun aynı olması beklenir.</span><span class="sxs-lookup"><span data-stu-id="758a9-128">The borrower commits to leaving the qubits in the same state they were in when they were borrowed,  i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="758a9-129">Özellikle bu durum klasik bir durum değildir; çoğu durumda, ödünç alınan kapsamlar ölçüm içermemelidir.</span><span class="sxs-lookup"><span data-stu-id="758a9-129">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="758a9-130">Qubits 'i ödünç alırken, sistem önce kullanımda olan ancak deyimin gövdesi sırasında erişilemeyen qubits 'lerden gelen isteği doldurmaya çalışacaktır `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="758a9-130">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="758a9-131">Bu tür qubit yoksa, isteği tamamlayacak yeni qubit ayırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="758a9-131">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>


<span data-ttu-id="758a9-132">Kirli qubits 'in bilinen kullanım durumları arasında, yalnızca çok az sayıda qubit ve incrementers uygulaması gerektiren çok kontrollü CNOT kapıları olan uygulamalardır.</span><span class="sxs-lookup"><span data-stu-id="758a9-132">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="758a9-133">[Örnek olarak](#borrowing-qubits-example) , soru-cevap veren bir algoritma için soru-cevap, düzenleme ve Toffoli tabanlı modüler çarpma (haner, Roetteler ve svore 2017) [*ile 2n + 2 qubit kullanma*](https://arxiv.org/abs/1611.07995) hakkında</span><span class="sxs-lookup"><span data-stu-id="758a9-133">See the [Borrowing Qubits Example](#borrowing-qubits-example) below to see an example of their use in Q#, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>


## <a name="intrinsic-operations"></a><span data-ttu-id="758a9-134">İç Işlemler</span><span class="sxs-lookup"><span data-stu-id="758a9-134">Intrinsic Operations</span></span>

<span data-ttu-id="758a9-135">Ayrıldıktan sonra, bir qubit daha sonra işlevlere ve işlemlere geçirilebilirler.</span><span class="sxs-lookup"><span data-stu-id="758a9-135">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="758a9-136">Bazı bir deyişle, bu, bir Q # programının bir qubit ile yapamalarıdır, ancak gerçekleştirilebilecek eylemler tüm işlemler olarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="758a9-136">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="758a9-137">Bu işlemleri, [Iç işlemler ve işlevlerde](xref:microsoft.quantum.libraries.standard.prelude)daha ayrıntılı bir şekilde görebiliyoruz, ancak şimdilik, qubits ile etkileşim kurmak için kullanılabilecek birkaç faydalı işlemden bahsedin.</span><span class="sxs-lookup"><span data-stu-id="758a9-137">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="758a9-138">İlk olarak, tek qubit Pauli Operators $X $, $Y $ ve $Z $, `X` `Y` her birinin türüne sahip olan iç işlemler, ve, ve `Z` her biri için Q # içinde temsil edilir `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="758a9-138">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="758a9-139">[Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude)bölümünde açıklandığı gibi, $X $ ve bu nedenle `X` bir bit çevirme işlemi olarak veya ağ geçidi değil, bu şekilde düşünebiliriz.</span><span class="sxs-lookup"><span data-stu-id="758a9-139">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="758a9-140">`X`İşlem, bazı klasik bit dizeler için $ \ket{s_0 s_1 \noktalara S_N} $ biçimindeki durumları hazırlamanızı sağlar $s $:</span><span class="sxs-lookup"><span data-stu-id="758a9-140">The `X` operation lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="758a9-141">Daha sonra, bu işlemi yazmak için el ile akış denetimi gerektirmeyen daha kompakt yollar görüyoruz.</span><span class="sxs-lookup"><span data-stu-id="758a9-141">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="758a9-142">Ayrıca, {0} {1} {2} {-} {0} {1} {2} iç Işlem tarafından Q # içinde temsil edilen Hadamard Transform $H $ ' i kullanarak $ \ket{+} = \left (\ket + \ket \ right)/\sqrt $ ve $ \ket = \left (\tus-\ket \ right)/\sqrt $ gibi durumları hazırlayabiliriz `H : (Qubit => Unit is Adj + Ctl)` :</span><span class="sxs-lookup"><span data-stu-id="758a9-142">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

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

## <a name="measurements"></a><span data-ttu-id="758a9-143">Ölçümler</span><span class="sxs-lookup"><span data-stu-id="758a9-143">Measurements</span></span>

<span data-ttu-id="758a9-144">`Measure`Yerleşik bir iç sıra olmayan işlem olan işlemi kullanarak, türü bir nesneden klasik bilgileri ayıklayabilir `Qubit` ve sonuç olarak bir klasik değer atayabiliriz ve `Result` Bu da sonucun artık hisse amamış olmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="758a9-144">Using the `Measure` operation, which is a built-in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span>
<span data-ttu-id="758a9-145">Girişi, `Measure` Bloch Sphere üzerinde, türü `Pauli` (örneğin, `PauliX` ) ve türünde bir değer ile temsil edilen bir Pauli ekseni `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="758a9-145">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by a value of type `Pauli` (for instance `PauliX`) and an value of type `Qubit`.</span></span>

<span data-ttu-id="758a9-146">Basit bir örnek, $ \ket $ durumunda bir qubit ayıran aşağıdaki işlemdir {0} , ardından buna bir Hadamard işlemi uygular `H` ve sonucu `PauliZ` temelde ölçer.</span><span class="sxs-lookup"><span data-stu-id="758a9-146">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

<span data-ttu-id="758a9-147">Aşağıdaki işlem tarafından biraz daha karmaşık bir örnek verilmiştir `true` ve bu tür bir kayıttaki tüm qubits `Qubit[]` 'ler, belirtilen bir Pauli tabanında ölçülerek sıfır durumunda ise ve aksi takdirde bu değer geri döndüğünde Boolean değeri döndürür `false` .</span><span class="sxs-lookup"><span data-stu-id="758a9-147">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

## <a name="borrowing-qubits-example"></a><span data-ttu-id="758a9-148">Ödünç alma qubits örneği</span><span class="sxs-lookup"><span data-stu-id="758a9-148">Borrowing Qubits Example</span></span>

<span data-ttu-id="758a9-149">Canon, `borrowing` anahtar sözcüğünü kullanan örnekler, örneğin, `MultiControlledXBorrow` aşağıda tanımlanan işlev.</span><span class="sxs-lookup"><span data-stu-id="758a9-149">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="758a9-150">`controls`Bir işleme eklenmesi gereken denetimi qubits 'e işaret ederseniz `X` , `Length(controls)-2` Bu uygulama tarafından birçok kirli ve daha fazla Las 'nin bir bütün olarak eklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="758a9-150">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="758a9-151">`With`Combinator---'ın, adjoint 'i destekleyen işlemler için geçerli olan (Bu örnekte,---) kapsamlı olarak kullanılması gerektiğini unutmayın `WithA` .</span><span class="sxs-lookup"><span data-stu-id="758a9-151">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example.</span></span>
<span data-ttu-id="758a9-152">Denetimi yalnızca iç işleme yayar içeren yapılara denetim eklemek için bu iyi bir programlama stilidir `With` .</span><span class="sxs-lookup"><span data-stu-id="758a9-152">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="758a9-153">Ayrıca, bu işlemin yanı sıra, işlem `body` `controlled` gövdesinin bir uygulamasının bir deyime yeniden değil, açıkça sağlandığını unutmayın `controlled auto` .</span><span class="sxs-lookup"><span data-stu-id="758a9-153">Further, note that here in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="758a9-154">Bunun nedeni, bağlantı hattı yapısından, her bir ve içindeki her bir kapıya denetim eklemeye kıyasla yararlı olan daha fazla denetimi nasıl kolayca ekleyebiliyoruz `body` .</span><span class="sxs-lookup"><span data-stu-id="758a9-154">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="758a9-155">Bu kodu başka bir Canon işleviyle karşılaştırmak `MultiControlledXClean` `X` , ancak mekanizmayı kullanarak birkaç temiz qubit kullanan, çarpma denetimli bir işlem uygulama amacını elde eder `using` .</span><span class="sxs-lookup"><span data-stu-id="758a9-155">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="758a9-156">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="758a9-156">Next steps</span></span>

<span data-ttu-id="758a9-157">Q # içindeki [Denetim akışı](xref:microsoft.quantum.guide.controlflow) hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="758a9-157">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>