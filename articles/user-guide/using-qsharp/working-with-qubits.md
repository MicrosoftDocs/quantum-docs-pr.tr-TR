---
title: Kubitlerle çalışma
description: İle qubits ile çalışma hakkında bilgi edinin Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: aa942a61280553ae4e51cd5ddcc85c0df935dab1
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835868"
---
# <a name="working-with-qubits"></a><span data-ttu-id="facca-103">Kubitlerle çalışma</span><span class="sxs-lookup"><span data-stu-id="facca-103">Working with qubits</span></span>

<span data-ttu-id="facca-104">Qubits, hisse bilgi işlem ortamında temel bilgilerin temel nesnesidir.</span><span class="sxs-lookup"><span data-stu-id="facca-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="facca-105">Qubits 'e genel bir bakış için bkz. [hisse parlaklığını anlama](xref:microsoft.quantum.overview.understanding)ve matematiksel gösterimlerine daha ayrıntılı bilgi için bkz. [qubit](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="facca-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="facca-106">Bu makalede, bir programda qubits 'in nasıl kullanılacağı ve bunlarla nasıl çalıştığı açıklanır Q# .</span><span class="sxs-lookup"><span data-stu-id="facca-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="facca-107">Bu makalede ele alınan deyimlerden hiçbiri bir işlevin gövdesinde geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="facca-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="facca-108">Bunlar yalnızca işlemler içinde geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="facca-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="facca-109">Qubit ayırma</span><span class="sxs-lookup"><span data-stu-id="facca-109">Allocating Qubits</span></span>

<span data-ttu-id="facca-110">Fiziksel qugeler, bir hisse bilgisayarında değerli bir kaynak olduğundan, derleyicinin işinin bir parçası mümkün olduğunca verimli şekilde kullanıldıklarından emin olmak.</span><span class="sxs-lookup"><span data-stu-id="facca-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="facca-111">Bu nedenle, Q# belirli bir ekstre bloğunda kullanmak üzere qubit *ayırmak* için söylemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="facca-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="facca-112">Qubits 'i tek bir qubit ya da *kayıt*olarak bilinen bir qubits dizisi olarak ayırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="facca-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register*.</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="facca-113">Qubit Temizleme</span><span class="sxs-lookup"><span data-stu-id="facca-113">Clean qubits</span></span>

<span data-ttu-id="facca-114">Bildirim `using` bloğu sırasında kullanılmak üzere yeni qubit ayırmak için ifadesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="facca-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="facca-115">İfade, anahtar sözcüğünden `using` , ardından parantez içine alınmış bir bağlama `( )` ve qubits 'in kullanılabildiği ifade bloğunun bir öğesinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="facca-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="facca-116">Bağlama deyimlerle aynı düzeni izler `let` : tek bir sembol veya sembol kümesi, ardından eşittir işareti `=` ve tek bir değer ya da eşleşen *Başlatıcı*grubu.</span><span class="sxs-lookup"><span data-stu-id="facca-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers*.</span></span>

<span data-ttu-id="facca-117">Başlatıcılar tek bir qubit için, `Qubit()` veya bir qubit dizisi olarak belirtilir, `Qubit[n]` burada `n` bir `Int` ifadedir.</span><span class="sxs-lookup"><span data-stu-id="facca-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="facca-118">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="facca-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="facca-119">Bu şekilde ayrılan her türlü qubit $ \ket {0} $ durumunda başlatılır.</span><span class="sxs-lookup"><span data-stu-id="facca-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="facca-120">Bu nedenle, önceki örnekte, `auxiliary` $ \ket $ durumunda tek bir qubit bulunur {0} ve `register` beş-qubit State $ {00000} \tus= \ket {0} \otimes \ayraç {0} \otimes \cnoktalar \otimes \ket $ ' de bulunur {0} .</span><span class="sxs-lookup"><span data-stu-id="facca-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="facca-121">`using`Bloğun sonunda, bu blok tarafından ayrılan tüm qubitleri hemen serbest bırakılır ve daha fazla kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="facca-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="facca-122">Hedef makineler serbest bırakılmış qugeler kullanabilir ve bunları `using` ayırma için diğer bloklara sunabilir.</span><span class="sxs-lookup"><span data-stu-id="facca-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="facca-123">Bu nedenle, hedef makine, bu qubits 'in {0} ayırmayı kaldırma işleminden hemen önce $ \ket $ durumunda olmasını bekler.</span><span class="sxs-lookup"><span data-stu-id="facca-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="facca-124">Mümkün olduğunda, tüm ayrılmış qubitleri $ \ket $ ' e döndürmek için Unitary işlemlerini kullanın {0} .</span><span class="sxs-lookup"><span data-stu-id="facca-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="facca-125">Gerekiyorsa, @"microsoft.quantum.intrinsic.reset" {0} bunu ölçerek ve sonuca göre koşullu bir işlem gerçekleştirerek, qubit ile $ \ket $ ' i döndüren işlemi kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="facca-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="facca-126">Bu tür bir ölçü, kalan qubits ile herhangi bir entanglement 'i yok eder ve bu sayede hesaplamayı etkileyebilir.</span><span class="sxs-lookup"><span data-stu-id="facca-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="facca-127">Ödünç alınan qubits</span><span class="sxs-lookup"><span data-stu-id="facca-127">Borrowed Qubits</span></span>

<span data-ttu-id="facca-128">`borrowing`Belirli bir durumda olması gerekmeyen, geçici kullanım için qubit ayırmak üzere ifadesini kullanın.</span><span class="sxs-lookup"><span data-stu-id="facca-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="facca-129">Hesaplama sırasında ödünç alınan qubits 'i boş alan olarak kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="facca-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="facca-130">Bu qubits genellikle temiz bir durumda değildir, diğer bir deyişle, $ \ket $ gibi bilinen bir durumda başlatılmamalıdır {0} .</span><span class="sxs-lookup"><span data-stu-id="facca-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="facca-131">Bunlar genellikle "kirli" qubit olarak adlandırılır, çünkü durumları bilinmez ve hatta hisse bilgisayar belleğinin diğer bölümleriyle eşit bir şekilde de olabilir.</span><span class="sxs-lookup"><span data-stu-id="facca-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="facca-132">Bağlama, ifadesiyle aynı model ve kurallara uyar `using` .</span><span class="sxs-lookup"><span data-stu-id="facca-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="facca-133">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="facca-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="facca-134">Ödünç alınan qubits, bilinmeyen bir durumda ve bildiri bloğunun sonundaki kapsam dışına çıkar.</span><span class="sxs-lookup"><span data-stu-id="facca-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="facca-135">Ödünç alma, qubits 'i ödünç aldıkları durum ile aynı durumda bırakarak, diğer bir deyişle, ekstre bloğunun başındaki ve sonundaki durum aynı olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="facca-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="facca-136">Bu durum klasik bir durum olmadığı için çoğu durumda, ödünç alınan kapsamlar ölçüm içermemelidir.</span><span class="sxs-lookup"><span data-stu-id="facca-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="facca-137">Qubits 'i ödünç alırken, sistem ilk olarak isteği kullanımda olan ancak deyimin gövdesinde erişilmeyen qubits 'lerden doldurmaya çalışır `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="facca-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="facca-138">Bu tür qubit yoksa, isteği tamamlaması için yeni qubit ayırır.</span><span class="sxs-lookup"><span data-stu-id="facca-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="facca-139">Kirli qubits 'in bilinen kullanım durumları arasında, yalnızca çok az sayıda qubit ve incrementers uygulaması gerektiren çok kontrollü CNOT kapıları olan uygulamalardır.</span><span class="sxs-lookup"><span data-stu-id="facca-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="facca-140">İçindeki kullanımları hakkında bir örnek için Q# , bu makaledeki [Qubitleri örnek olarak ödünç](#borrowing-qubits-example) alma veya düzenleme kağıt, [*Toffoli tabanlı modüler çarpma*](https://arxiv.org/abs/1611.07995) (haner, Roetteler ve svore 2017) ile birlikte, ödünç alınan qubits kullanan bir algoritma için bkz. 2.</span><span class="sxs-lookup"><span data-stu-id="facca-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="facca-141">İç Işlemler</span><span class="sxs-lookup"><span data-stu-id="facca-141">Intrinsic Operations</span></span>

<span data-ttu-id="facca-142">Ayrıldıktan sonra işlevlere ve işlemlere bir qubit geçirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="facca-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="facca-143">Bazı bir deyişle, bir Q# programın bir qubit ile yapamamaları, ancak gerçekleştirilebilecek eylemler tüm işlemler olarak tanımlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="facca-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="facca-144">Bu makalede, Q# qubits ile etkileşim kurmak için kullanabileceğiniz birkaç faydalı işlem ele alınmaktadır.</span><span class="sxs-lookup"><span data-stu-id="facca-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="facca-145">Bunlar ve diğerleri hakkında daha fazla ayrıntı için bkz. [Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude).</span><span class="sxs-lookup"><span data-stu-id="facca-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="facca-146">İlk olarak, tek qubit Pauli Operators $X $, $Y $ ve $Z $, Q# [`X`](xref:microsoft.quantum.intrinsic.x) [`Y`](xref:microsoft.quantum.intrinsic.y) [`Z`](xref:microsoft.quantum.intrinsic.z) her birinin türüne sahip olan iç işlemler, ve, ile temsil edilir `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="facca-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:microsoft.quantum.intrinsic.x), [`Y`](xref:microsoft.quantum.intrinsic.y), and [`Z`](xref:microsoft.quantum.intrinsic.z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="facca-147">[Iç işlemler ve işlevler](xref:microsoft.quantum.libraries.standard.prelude)bölümünde açıklandığı gibi, $X $ ve bu nedenle, `X` bir bit çevirme işlemi veya ağ geçidi değil olarak düşünün.</span><span class="sxs-lookup"><span data-stu-id="facca-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="facca-148">`X`Bazı klasik bit dizeler için $ \ket{s_0 s_1 \noktalara S_N} $ biçimindeki durumları hazırlamak için bu işlemi kullanabilirsiniz $s $:</span><span class="sxs-lookup"><span data-stu-id="facca-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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
> <span data-ttu-id="facca-149">Daha sonra, bu işlemi yazmak için el ile denetim akışı gerektirmeyen daha kompakt yollar görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="facca-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="facca-150">Ayrıca, $ \ket{+} = \left (\ket {0} + \ket {1} \ right)/\sqrt {2} $ ve $ \ket {-} = \left (\tus- {0} \ket {1} \ right)/\Sqrt $ gibi durumları, {2} Hadamard Transform $H $ kullanarak da hazırlayabilirsiniz. Q# iç işlem tarafından temsil edilen [`H`](xref:microsoft.quantum.intrinsic.h) (qubit => Unit, sıfatı + CTL) '):</span><span class="sxs-lookup"><span data-stu-id="facca-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:microsoft.quantum.intrinsic.h) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

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

## <a name="measurements"></a><span data-ttu-id="facca-151">Ölçümler</span><span class="sxs-lookup"><span data-stu-id="facca-151">Measurements</span></span>

<span data-ttu-id="facca-152">Tek tek qubit ölçümleri, her biri [Bloch Sphere](xref:microsoft.quantum.glossary#bloch-sphere)üzerinde bir Pauli ekseni tarafından temsil edilen farklı tabanlarda gerçekleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="facca-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="facca-153">*Hesaplama temeli* temel anlamına gelir `PauliZ` ve ölçüm için en yaygın olarak kullanılan temeldir.</span><span class="sxs-lookup"><span data-stu-id="facca-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="facca-154">Temelde tek bir qubit ölçme `PauliZ`</span><span class="sxs-lookup"><span data-stu-id="facca-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="facca-155">[`M`](xref:microsoft.quantum.intrinsic.m)Temelinde tek bir qubit ölçmek `PauliZ` ve sonuca bir klasik değer atamak için yerleşik bir içsel Unitary işlemi olan işlemi kullanın.</span><span class="sxs-lookup"><span data-stu-id="facca-155">Use the [`M`](xref:microsoft.quantum.intrinsic.m) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="facca-156">`M` , `Result` yalnızca değer `Zero` `One` elde eden veya ölçülen durum $ \ket {0} $ veya $ \ket {1} $-sonucu yalnızca bir hisse</span><span class="sxs-lookup"><span data-stu-id="facca-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="facca-157">Basit bir örnek, $ \ket $ durumunda bir qubit ayıran aşağıdaki işlemdir {0} , ardından buna bir Hadamard işlemi uygular `H` ve sonucu `PauliZ` temelde ölçer.</span><span class="sxs-lookup"><span data-stu-id="facca-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

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

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="facca-158">Belirli tabanlarda bir veya daha fazla qubit ölçme</span><span class="sxs-lookup"><span data-stu-id="facca-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="facca-159">Belirli tabanlarda bir veya daha fazla qubit dizisini ölçmek için, [`Measure`](xref:microsoft.quantum.intrinsic.measure) işlemini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="facca-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:microsoft.quantum.intrinsic.measure) operation.</span></span>

<span data-ttu-id="facca-160">İçin girdiler, `Measure` türlerin bir dizisidir `Pauli` (örneğin, `[PauliX, PauliZ, PauliZ]` ) ve bir qubit dizisidir.</span><span class="sxs-lookup"><span data-stu-id="facca-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="facca-161">Aşağıdaki işlem tarafından biraz daha karmaşık bir örnek verilmiştir `true` ve bu tür bir kayıttaki tüm qubits `Qubit[]` 'ler, belirtilen bir Pauli tabanında ölçülerek sıfır durumunda ise ve aksi takdirde bu değer geri döndüğünde Boolean değeri döndürür `false` .</span><span class="sxs-lookup"><span data-stu-id="facca-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

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

<span data-ttu-id="facca-162">Bu örneğin `Measure` her seferinde yalnızca tek bir qubits üzerinde devam ettiğinden, ancak işlem birden çok qubit üzerinde birlikte bulunan ölçümlere genişletilebilir.</span><span class="sxs-lookup"><span data-stu-id="facca-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="facca-163">Ödünç alma qubits örneği</span><span class="sxs-lookup"><span data-stu-id="facca-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="facca-164">`borrowing`Aşağıdaki işlev gibi, Canon anahtar sözcüğünü kullanan örnekler vardır `MultiControlledXBorrow` .</span><span class="sxs-lookup"><span data-stu-id="facca-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="facca-165">`controls`Denetimi bir işleme eklemek için denetim qubits 'e işaret ederseniz `X` , bu uygulama tarafından eklenen kirli [ancillas](xref:microsoft.quantum.glossary#ancilla) bir ve daha fazla değer vardır `Length(controls)-2` .</span><span class="sxs-lookup"><span data-stu-id="facca-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

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

<span data-ttu-id="facca-166">Bu örnekte,, `With` Örneğin, adjoint 'i destekleyen işlemler için geçerli olan Combinator 'ın kapsamlı kullanımını kullandığına unutmayın `WithA` .</span><span class="sxs-lookup"><span data-stu-id="facca-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="facca-167">Denetimi yalnızca iç işleme yayar içeren yapılara denetim eklemek için bu iyi bir programlama stilidir `With` .</span><span class="sxs-lookup"><span data-stu-id="facca-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="facca-168">Ayrıca, işlemin yanı sıra, `body` `controlled` bir ifadeye daha sonra değil, işlemin gövde bir uygulamasının açıkça sağlandığını unutmayın `controlled auto` .</span><span class="sxs-lookup"><span data-stu-id="facca-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="facca-169">Bunun nedeni, devrenin yapısı nedeniyle, içindeki her bir kapıya denetim eklemeye kıyasla yararlı olan daha fazla denetim eklemek kolaydır `body` .</span><span class="sxs-lookup"><span data-stu-id="facca-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="facca-170">Bu kodu başka bir Canon işleviyle karşılaştırmak `MultiControlledXClean` `X` , ancak mekanizmayı kullanarak birkaç temiz qubit kullanan, çarpma denetimli bir işlem uygulama amacını elde eder `using` .</span><span class="sxs-lookup"><span data-stu-id="facca-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="facca-171">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="facca-171">Next steps</span></span>

<span data-ttu-id="facca-172">İçindeki [Denetim akışı](xref:microsoft.quantum.guide.controlflow) hakkında bilgi edinin Q# .</span><span class="sxs-lookup"><span data-stu-id="facca-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>