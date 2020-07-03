---
title: "Q 'daki işlemler ve işlevler #"
description: İşlem ve işlevlerin yanı sıra denetlenen ve Adjoint işlem uzmanlıklarını tanımlama ve çağırma.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 08eaf150a38afd789f8a23f567ff111d002bac07
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884210"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="af866-103">Q 'daki işlemler ve Işlevler #</span><span class="sxs-lookup"><span data-stu-id="af866-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="af866-104">Yeni Işlemleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="af866-104">Defining New Operations</span></span>

<span data-ttu-id="af866-105">İşlemler, Q # ' ın temel sayısıdır.</span><span class="sxs-lookup"><span data-stu-id="af866-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="af866-106">Bildirdikten sonra, klasik .NET uygulamalarından çağrılabilir; Örneğin, simülatör veya Q # içinde başka işlemler olabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="af866-107">Q # içinde tanımlanan her işlem, dil tarafından tanımlanan yerleşik iç işlemler de dahil olmak üzere herhangi bir sayıda işlemi çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="af866-108">Bu iç işlemleri Q # ' ın tanımladığı belirli yol, hedef makineye bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="af866-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="af866-109">Derlendiğinde, her işlem hedef makinelere sağlanlenebilecek bir .NET sınıf türü olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="af866-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="af866-110">Her Q # kaynak dosyası herhangi bir sayıda işlem tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="af866-111">İşlem adları ad alanı içinde benzersiz olmalıdır ve tür veya işlev adlarıyla çakışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="af866-112">İşlem bildirimi, anahtar sözcüğünden ve `operation` ardından işlemin adı olan sembol, işlem için bağımsız değişkenleri tanımlayan türü belirlenmiş bir tanımlayıcı tanımlama grubu, iki nokta üst üste `:` , işlemin sonuç türünü açıklayan bir tür açıklaması, isteğe bağlı olarak işlem özellikleri olan bir ek açıklama, bir açık küme ayracı ve sonra da işlem bildiriminin gövdesini içerir `{ }` .</span><span class="sxs-lookup"><span data-stu-id="af866-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="af866-113">Her işlem bir girdi alır, bir çıktı üretir ve bir veya daha fazla işlem uzmanlığını için uygulamayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="af866-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="af866-114">Olası Uzmanlıklar ve bunların nasıl tanımlanacağı ve çağrılacağını, bu makalenin farklı bölümlerinde ayrıntılı olarak açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="af866-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="af866-115">Şimdilik yalnızca bir varsayılan gövde özelleştirmesi tanımlayan ve giriş olarak tek bir qubit alan aşağıdaki işlemi göz önünde bulundurun ve sonra <xref:microsoft.quantum.intrinsic.x> Bu girişte yerleşik işlemi çağırır:</span><span class="sxs-lookup"><span data-stu-id="af866-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="af866-116">Anahtar sözcüğü, `operation` işlem tanımını ve ardından adı ile başlar; burada, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="af866-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="af866-117">Sonra, giriş türü, `Qubit` `target` Yeni işlemdeki girişe başvurmak için bir adla birlikte tanımlanır ().</span><span class="sxs-lookup"><span data-stu-id="af866-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="af866-118">Son olarak, `Unit` işlemin çıktısının boş olduğunu tanımlar.</span><span class="sxs-lookup"><span data-stu-id="af866-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="af866-119">`Unit`, `void` C# ve diğer zorunlu dillerde aynı şekilde kullanılır ve `unit` F # ve diğer işlevsel dillerde eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="af866-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="af866-120">İşlemler Ayrıca, öğesinden daha ilginç türler de döndürebilir `Unit` .</span><span class="sxs-lookup"><span data-stu-id="af866-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="af866-121">Örneğin, işlem, <xref:microsoft.quantum.intrinsic.m> `Result` ölçüm gerçekleştirmemiş olduğunu temsil eden türünde bir çıktı döndürür.</span><span class="sxs-lookup"><span data-stu-id="af866-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="af866-122">Bir işlemden başka bir işleme geçirebilirsiniz veya `let` Yeni bir değişken tanımlamak için anahtar sözcükle birlikte kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af866-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="af866-123">Bu yaklaşım, en [yoğun kodlama](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)gibi düşük bir düzeyde hisse uygun olan klasik hesaplamayı temsil etmenizi sağlar:</span><span class="sxs-lookup"><span data-stu-id="af866-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> <span data-ttu-id="af866-124">Q # içindeki her işlem tam olarak bir giriş alır ve tam olarak bir çıkış döndürür.</span><span class="sxs-lookup"><span data-stu-id="af866-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="af866-125">Birden çok giriş ve çıkış, birden çok değeri birlikte tek bir değerde depolayan *Tanımlama grupları*kullanılarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="af866-125">Multiple inputs and outputs are represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="af866-126">Bu şekilde, Q #, "kayıt düzeni oluşturma" dilidir.</span><span class="sxs-lookup"><span data-stu-id="af866-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="af866-127">Bu kavramı takip eden bir dizi boş parantezler, `()` daha sonra türü olan "boş" kayıt düzeni olarak okunmalıdır `Unit` .</span><span class="sxs-lookup"><span data-stu-id="af866-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="af866-128">Denetlenen ve Adjoint Işlemleri</span><span class="sxs-lookup"><span data-stu-id="af866-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="af866-129">Bir işlem, bir Unitary dönüştürmesi uygularsa, Q # içindeki birçok işlem için durum olduğu gibi, *adjointed* veya *denetimli*olduğunda işlemin nasıl davrandığını tanımlamak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="af866-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="af866-130">Bir işlemin *adjoint* özelleştirmesi işlemin nasıl davranması gerektiğini belirtir, *denetimli* bir özelleşme, uygulamanın belirli bir hisse kaydı durumunda olduğu durumlarda bir işlemin nasıl davranması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="af866-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="af866-131">Hisse unsurlarının bir bölümünü, hisse bilgi işlem işlemlerinin birçok yönü için çok önemlidir.</span><span class="sxs-lookup"><span data-stu-id="af866-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="af866-132">Faydalı bir Q # programlama tekniğinden oluşan bir örnek için, bu makaledeki [conjugations](#conjugations) bakın.</span><span class="sxs-lookup"><span data-stu-id="af866-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Conjugations](#conjugations) in this article.</span></span> 

<span data-ttu-id="af866-133">Bir işlemin denetlenen sürümü, yalnızca tüm denetim qubits 'in belirtilen durumda olması durumunda temel işlemi etkili bir şekilde uygulayan yeni bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="af866-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="af866-134">Denetim qubitleri üst konumundayken, temel işlem üst konumun uygun bölümüne doğru şekilde uygulanır.</span><span class="sxs-lookup"><span data-stu-id="af866-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="af866-135">Bu nedenle, denetimli işlemler genellikle entanglement oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="af866-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="af866-136">Doğal olarak, *denetlenen bir adjoint* özelleştirmesi de bir işlemin adjoint öğesinin denetimli uygulamasını belirterek bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="af866-137">$U $, bir işlem tarafından uygulanan Unitary dönüşümünde `U` , `Adjoint U` karmaşık eşleniği devrik olan "^ \dağılım $ $U Unitary dönüşümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="af866-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="af866-138">Bir işlemin büyük bir bir şekilde uygulanması ve sonra adekliği, bu durum, $UU ^ \gger = U ^ \gger U = \ID $, kimlik matrisi olan olgu tarafından gösterildiği gibi durumu değişmeden bırakır.</span><span class="sxs-lookup"><span data-stu-id="af866-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="af866-139">Denetlenen bir işlemin Unitary temsili biraz daha fazla bir işlemdir, ancak daha fazla ayrıntı için [hisse bilgi işlem kavramlarıyla daha fazla bilgi bulabilirsiniz: birden çok qubit](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="af866-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="af866-140">Aşağıdaki bölümde, bu çeşitli uzmanların Q # kodunuzda nasıl çağrılacağını ve bunları desteklemek için işlemlerin nasıl tanımlanacağı açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="af866-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="af866-141">İşlem uzmanlık işlemleri çağrılıyor</span><span class="sxs-lookup"><span data-stu-id="af866-141">Calling operation specializations</span></span>

<span data-ttu-id="af866-142">Q # ' daki bir *functor* , başka bir işlemden yeni bir işlem tanımlayan bir fabrikadır.</span><span class="sxs-lookup"><span data-stu-id="af866-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="af866-143">Q # içindeki iki standart komik `Adjoint` ve ' dir `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="af866-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="af866-144">Funörler, yeni işlemin uygulamasını tanımlarken temel işlemin uygulamasına erişebilir.</span><span class="sxs-lookup"><span data-stu-id="af866-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="af866-145">Bu nedenle, funörler geleneksel daha yüksek düzey işlevlerden daha karmaşık işlevler gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="af866-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="af866-146">Funörler, Q # tür sisteminde bir gösterimine sahip değildir.</span><span class="sxs-lookup"><span data-stu-id="af866-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="af866-147">Bu nedenle, şu anda bunları bir değişkene bağlamak veya bağımsız değişken olarak geçirmek mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="af866-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="af866-148">Yeni bir işlem döndüren bir işleme uygulayarak bir functor kullanın.</span><span class="sxs-lookup"><span data-stu-id="af866-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="af866-149">Örneğin, `Adjoint` işlem için functor uygulandığında `Y` Yeni işlem döndürülür `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="af866-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="af866-150">Yeni işlemi başka bir işlem gibi çağırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af866-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="af866-151">Bir işlemin veya komik uygulamalarının uygulamasını desteklemesi için `Adjoint` `Controlled` dönüş türünün olması gerekir `Unit` .</span><span class="sxs-lookup"><span data-stu-id="af866-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="af866-152">`Adjoint`functor</span><span class="sxs-lookup"><span data-stu-id="af866-152">`Adjoint` functor</span></span>

<span data-ttu-id="af866-153">Bu nedenle, `Adjoint Y(q1)` `Adjoint` `Y` Yeni bir işlem oluşturmak için functor işlemini uygular ve bu yeni işlemi öğesine uygular `q1` .</span><span class="sxs-lookup"><span data-stu-id="af866-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="af866-154">Yeni işlem, temel işlemle aynı imzaya ve türe sahip `Y` .</span><span class="sxs-lookup"><span data-stu-id="af866-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="af866-155">Özellikle, yeni işlem de destekler `Adjoint` ve `Controlled` yalnızca temel işlem olduysa, ve desteklenir.</span><span class="sxs-lookup"><span data-stu-id="af866-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="af866-156">`Adjoint`Functor kendi tersidir; diğer bir deyişle, `Adjoint Adjoint Op` her zaman ile aynıdır `Op` .</span><span class="sxs-lookup"><span data-stu-id="af866-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="af866-157">`Controlled`functor</span><span class="sxs-lookup"><span data-stu-id="af866-157">`Controlled` functor</span></span>

<span data-ttu-id="af866-158">Benzer şekilde, `Controlled X(controls, target)` `Controlled` `X` Yeni bir işlem oluşturmak için functor işlemini uygular ve bu yeni işlemi ve için uygular `controls` `target` .</span><span class="sxs-lookup"><span data-stu-id="af866-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="af866-159">Q # ' da, denetlenen sürümler her zaman bir denetim qubit dizisini alır ve denetim her zaman hesaplama () durumunda olan tüm denetim qubits 'i `PauliZ` `One` $ \tus$ ' i temel alır {1} .</span><span class="sxs-lookup"><span data-stu-id="af866-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="af866-160">Diğer durumlara göre denetlemek, denetimli işlemden önce denetim qubits 'e uygun Unitary işlemini uygulayarak ve sonra, denetimli işlemden sonra Unitary işleminin evirimini uygulayarak elde edilir.</span><span class="sxs-lookup"><span data-stu-id="af866-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="af866-161">Örneğin, `X` denetimli bir işlemden önce ve sonra bir işlemi bir denetim qubit uygulamak, `Zero` Bu qubit için ($ \ket $) durumunda işlemin denetlenmesini sağlar {0} ; durum `H` üzerinde ve sonrasında denetimleri `PauliX` `One` , durum yerine Pauli X, $ \tus\mathrel{ {-} : =} (\tus- {0} {1} \tus)/\sqrt {2} $ olan `PauliZ` `One` -1.</span><span class="sxs-lookup"><span data-stu-id="af866-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="af866-162">Bir işlem ifadesi verildiğinde, functor kullanarak yeni bir işlem ifadesi oluşturabilirsiniz `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="af866-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="af866-163">Yeni işlemin imzası, özgün işlemin imzasını temel alır.</span><span class="sxs-lookup"><span data-stu-id="af866-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="af866-164">Sonuç türü aynıdır, ancak giriş türü, ilk öğe olarak denetim qubit dizisini ve ikinci öğe olarak orijinal işlemin bağımsız değişkenlerini tutan bir qubit dizisi olan iki kayıt türüdür.</span><span class="sxs-lookup"><span data-stu-id="af866-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="af866-165">Yeni işlem `Controlled` ' i destekler ve `Adjoint` yalnızca özgün işlem olduysa, ve yalnızca bunu destekler.</span><span class="sxs-lookup"><span data-stu-id="af866-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="af866-166">Özgün işlem yalnızca tek bir bağımsız değişken alıyorsa, tek [demet denklik](xref:microsoft.quantum.guide.types) , burada oynat olarak gelir.</span><span class="sxs-lookup"><span data-stu-id="af866-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="af866-167">Örneğin, `Controlled X` işlemin denetlenen sürümüdür `X` .</span><span class="sxs-lookup"><span data-stu-id="af866-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="af866-168">`X`türüne sahip `(Qubit => Unit is Adj + Ctl)` , `Controlled X` Bu nedenle türüne sahip `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` . tek kayıt düzeni denkliği nedeniyle bu, ile aynıdır `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="af866-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="af866-169">Temel işlem birkaç bağımsız değişken alıyorsa, bu işlemin denetlenen sürümünün ilgili bağımsız değişkenlerini, bir tanımlama grubu içine dönüştürmek için parantez içine almayı unutmayın.</span><span class="sxs-lookup"><span data-stu-id="af866-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="af866-170">Örneğin, `Controlled Rz` işlemin denetlenen sürümüdür `Rz` .</span><span class="sxs-lookup"><span data-stu-id="af866-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="af866-171">`Rz`türüne sahip `((Double, Qubit) => Unit is Adj + Ctl)` , bu nedenle `Controlled Rz` türüne sahip `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="af866-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="af866-172">Bu nedenle, `Controlled Rz(controls, (0.1, target))` geçerli bir çağrısı olur `Controlled Rz` (etrafındaki ayraçları aklınızda bulunan `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="af866-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="af866-173">Başka bir örnek olarak, `CNOT(control, target)` olarak uygulanabilir `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="af866-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="af866-174">Bir hedefin iki denetim qubits (CCNOT) tarafından denetlenmesi gerekiyorsa, bir `Controlled X([control1, control2], target)` ifade kullanın.</span><span class="sxs-lookup"><span data-stu-id="af866-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="af866-175">`Controlled`Ve `Adjoint` komik, ve uygulama arasında bir fark yoktur `Controlled Adjoint Op` `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="af866-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="af866-176">Denetlenen ve Adjoint uygulamalarını tanımlama</span><span class="sxs-lookup"><span data-stu-id="af866-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="af866-177">Önceki örneklerde ilk işlem bildiriminde, işlemler `BitFlip` ve `DecodeSuperdense` sırasıyla imzalar ve ile tanımlanmıştır `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .</span><span class="sxs-lookup"><span data-stu-id="af866-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="af866-178">`DecodeSuperdense`Ölçümler de dahil olmak üzere, Unitary bir işlem değildir ve bu nedenle hiçbir adeksel uzmanlık yok (Bu, bu tür bir işlemin döndürdüğü ilgili gereksinimi geri çağırır `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="af866-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="af866-179">Ancak, `BitFlip` yalnızca Unitary işlemini gerçekleştirdiğinden, <xref:microsoft.quantum.intrinsic.x> bunu her iki uzmanlıklarla tanımlamış olabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af866-179">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="af866-180">Bu bölümde, Q # işlem bildirimlerinizde özelleştirilmiş uygulanmaları 'nın nasıl dahil olduğu açıklanır ve bu nedenle, `Adjoint` veya funlar ile birlikte çağrılabilir `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="af866-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="af866-181">Bazı durumlar hakkında daha fazla bilgi edinmek için geçerli olduğu veya bazı Uzmanlıkları bildirmek için geçerli olmayan durumlar hakkında daha fazla bilgi için, bu makaledeki [özelleştirilmiş oluşturmaları Ilgili koşullar](#circumstances-for-validly-defining-specializations) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="af866-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="af866-182">İşlem özellikleri, bildirildiği işleme ne tür işlevler uygulayabileceğinizi ve sahip oldukları etkiyi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="af866-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="af866-183">Bu uzmanlıklardan biri, özellikle işlem özelliklerine sahip bir ek açıklama aracılığıyla işlem imzasının bir parçası olarak bildirilemez: `is Adj` ,, `is Ctl` veya `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="af866-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="af866-184">Her özelleştirmenin gerçek uygulama *örtük* veya *Açık* bir şekilde tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="af866-185">Örtük olarak uygulamaları belirtme</span><span class="sxs-lookup"><span data-stu-id="af866-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="af866-186">Bu durumda, işlem bildiriminin gövdesi yalnızca varsayılan uygulamadan oluşur.</span><span class="sxs-lookup"><span data-stu-id="af866-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="af866-187">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="af866-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="af866-188">Burada, örtük olarak tanımlanmış her bir özelleştirme için karşılık gelen uygulama, veya komik kullanılıyorsa, derleyici tarafından otomatik olarak oluşturulur `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="af866-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="af866-189">Bu nedenle, bir çağrısı `Adjoint PrepareEntangledPair` derleyicinin adekini `CNOT` ve sonra adekini uygulamasına neden olur `H` .</span><span class="sxs-lookup"><span data-stu-id="af866-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="af866-190">Bu bireysel işlemler kendi kendine adekdir, bu nedenle sonuçtaki `Adjoint PrepareEntangledPair` işlem yalnızca uygulama `CNOT(here, there)` ve ardından oluşur `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="af866-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="af866-191">Bu nedenle, `DecodeSuperdense` `PrepareEntangledPair` entangled durumunu bir qubit çiftiyle geri dönüştürmek için adjoint öğesini kullanarak önceki örneğe daha fazla sıkı yazmak için bunu kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="af866-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="af866-192">Bildirimin işlem özellikleriyle birlikte ek açıklama, derleyicinin varsayılan uygulamaya göre diğer özelleştirmeleri otomatik olarak üretmesinin güvence altına almak için yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="af866-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="af866-193">Funlar ile kullanım için işlemleri tasarlarken göz önünde bulundurmanız gereken birkaç önemli sınırlama vardır.</span><span class="sxs-lookup"><span data-stu-id="af866-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="af866-194">Aynı etkiyi elde etmek için bu tür bir işlemde deyimleri yeniden sıralamak belirsiz olduğundan, başka bir *işlemin çıkış* değerini kullanan bir işlem için en kritik öneme sahip olan uzmanlık, derleyici tarafından otomatik olarak üretilemez.</span><span class="sxs-lookup"><span data-stu-id="af866-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="af866-195">Bu nedenle, genellikle çeşitli uygulamaları açıkça belirtmek yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="af866-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="af866-196">Uygulamaları açıkça belirtme</span><span class="sxs-lookup"><span data-stu-id="af866-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="af866-197">Derleyicinin uygulamayı oluşturabileceği durumda, bunu açıkça belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af866-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="af866-198">Bu tür açık özelleşmeler, uygun bir *oluşturma yönergesinin* veya Kullanıcı tanımlı bir uygulamadan oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="af866-199">Aşağıda, bazı açık özelleşmeye örnek olarak tüm olasılıklar verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="af866-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="af866-200">Açık Özelleştirme bildirimleri</span><span class="sxs-lookup"><span data-stu-id="af866-200">Explicit specialization declarations</span></span>

<span data-ttu-id="af866-201">S # işlemleri aşağıdaki açık özelleştirme bildirimlerini içerebilir:</span><span class="sxs-lookup"><span data-stu-id="af866-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="af866-202">`body`Özelleşme, hiçbir komik uygulanmamış şekilde işlemin uygulanmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="af866-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="af866-203">`adjoint`Özelleşme, işlem için `Adjoint` functor uygulanmış olan uygulamayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="af866-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="af866-204">`controlled`Özelleşme, işlem için `Controlled` functor uygulanmış olan uygulamayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="af866-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="af866-205">`controlled adjoint`Özelleşme, hem hem de `Adjoint` funları uygulanan işlemin uygulanmasını belirtir `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="af866-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="af866-206">Bu özelleşme `adjoint controlled` , iki komik bulunduğu için de adlandırılmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="af866-207">Bir işlem özelleştirmesi, özelleştirme etiketinden oluşur (örneğin, `body` veya) ve `adjoint` aşağıdakilerden biri:</span><span class="sxs-lookup"><span data-stu-id="af866-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="af866-208">Aşağıda açıklandığı gibi açık bir bildirim.</span><span class="sxs-lookup"><span data-stu-id="af866-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="af866-209">Derleyiciye özelleştirmenin *nasıl* oluşturulacağını belirten bir *yönerge* , aşağıdakilerden biri:</span><span class="sxs-lookup"><span data-stu-id="af866-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="af866-210">`intrinsic`, hedef makinenin özelleşme sağladığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="af866-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="af866-211">`distribute`, `controlled` ve `controlled adjoint` uzmanlıklarıyla kullanılır.</span><span class="sxs-lookup"><span data-stu-id="af866-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="af866-212">İle kullanıldığında `controlled` , derleyicinin `Controlled` , içindeki tüm işlemlere uygulanarak özelleştirmeyi hesaplaması gerektiğini belirtir `body` .</span><span class="sxs-lookup"><span data-stu-id="af866-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="af866-213">İle kullanıldığında `controlled adjoint` , derleyicinin özelleşmenin tüm işlemlerine uygulayarak özelleştirmeyi hesaplaması gerektiğini belirtir `Controlled` `adjoint` .</span><span class="sxs-lookup"><span data-stu-id="af866-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="af866-214">`invert`, `adjoint` `body` Örneğin, örneğin, işlem sırasını ters çevirerek ve adeki her birine uygulayarak, derleyicinin özelleştirmeyi hesaplaması gerektiğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="af866-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="af866-215">İle kullanıldığında `adjoint controlled` , bu, derleyicinin özelleştirmeyi ters çeviren şekilde özelleşmesi gerektiğini belirtir `controlled` .</span><span class="sxs-lookup"><span data-stu-id="af866-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="af866-216">`self`, adjoint özelleşmenin özelleştirme ile aynı olduğunu göstermek için `body` .</span><span class="sxs-lookup"><span data-stu-id="af866-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="af866-217">Kullanımı `self` ve uzmanlık için geçerlidir `adjoint` `adjoint controlled` .</span><span class="sxs-lookup"><span data-stu-id="af866-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="af866-218">İçin `adjoint controlled` , `self` `adjoint controlled` özelleştirmenin özelleştirme ile aynı olduğunu gösterir `controlled` .</span><span class="sxs-lookup"><span data-stu-id="af866-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="af866-219">`auto`, derleyicinin uygulanacak uygun bir yönergeyi seçmesini belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="af866-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="af866-220">`auto`Özelleştirme için kullanamazsınız `body` .</span><span class="sxs-lookup"><span data-stu-id="af866-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="af866-221">Yönergelerin ve `auto` tümünün bir kapanış noktalı virgül olması gerekir `;` .</span><span class="sxs-lookup"><span data-stu-id="af866-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="af866-222">`auto`Bir açık bildirimi sağlanmışsa, yönergesi aşağıdaki oluşturulan yönergeyi çözümler `body` :</span><span class="sxs-lookup"><span data-stu-id="af866-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="af866-223">`adjoint`Özelleşme, yönergeye göre oluşturulur `invert` .</span><span class="sxs-lookup"><span data-stu-id="af866-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="af866-224">`controlled`Özelleşme, yönergeye göre oluşturulur `distribute` .</span><span class="sxs-lookup"><span data-stu-id="af866-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="af866-225">`adjoint controlled` `invert` İçin açık bir bildirime izin `controlled` verildiğinde ve yoksa, özelleştirme yönergeye göre oluşturulur `adjoint` `distribute` .</span><span class="sxs-lookup"><span data-stu-id="af866-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="af866-226">Bir işlem kendi kendine adekiyiyise, `self` derleyicinin en iyi duruma getirme amacıyla bu bilgileri kullanmasına izin vermek için oluşturma yönergesi aracılığıyla adjoint veya denetimli adjoint özelleşmesini açıkça belirtin.</span><span class="sxs-lookup"><span data-stu-id="af866-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="af866-227">Kullanıcı tanımlı bir uygulama içeren bir özelleştirme bildirimi, bir bağımsız değişken kayıt kümesinden ve ardından, özelleştirmeyi uygulayan Q # koduna sahip bir ekstre bloğundan oluşur.</span><span class="sxs-lookup"><span data-stu-id="af866-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="af866-228">Bağımsız değişken listesinde, `...` işlem için belirtilen bağımsız değişkenleri bir bütün olarak temsil etmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="af866-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="af866-229">`body`Ve için `adjoint` bağımsız değişken listesi her zaman olmalıdır `(...)` ; ve için `controlled` `adjoint controlled` bağımsız değişken listesi, denetim qubits dizisini temsil eden bir sembol olmalıdır `...` ; Örneğin, parantez içine alınmış `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="af866-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="af866-230">Örnekler</span><span class="sxs-lookup"><span data-stu-id="af866-230">Examples</span></span>

<span data-ttu-id="af866-231">İşlem bildirimi, temel Pauli X işlemini tanımlayan aşağıdaki kadar basit olabilir:</span><span class="sxs-lookup"><span data-stu-id="af866-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="af866-232">Pauli X işleminin adjoint değeri, `self` tanım tarafından kendi tersi olduğundan, yönergeyle tanımlandığını unutmayın `X` .</span><span class="sxs-lookup"><span data-stu-id="af866-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="af866-233">Önceki `PrepareEntangledPair` örnekte, kod açık özelleştirme bildirimlerini içeren aşağıdaki koda eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="af866-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="af866-234">Anahtar sözcüğü, `auto` derleyicinin nasıl özelleşdiğini uygulamanın nasıl oluşturulacağını belirlemesi gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="af866-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="af866-235">Kullanıcı tanımlı özelleştirme uygulama</span><span class="sxs-lookup"><span data-stu-id="af866-235">User-defined specialization implementation</span></span>

<span data-ttu-id="af866-236">Derleyici belirli bir özelleşmenin uygulamasını otomatik olarak üretemiyor veya daha verimli bir uygulama verilirse, uygulamayı el ile tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af866-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="af866-237">Önceki örnekte, `adjoint invert;` adjoint özelleşmesinin, gövde uygulamasını tersine çeviren ve denetlenen `controlled adjoint invert;` majoint özelleşmesinin, denetlenen özelleşmenin belirtilen uygulamasını tersine ayırarak oluşturulacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="af866-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="af866-238">Varsayılan gövdenin yanı sıra bir veya daha fazla özelleştirilmiş açıkça bildirilmesi gerekiyorsa, varsayılan gövdeye yönelik uygulamanın uygun bir özelleştirme bildirimine de sarmalanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="af866-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="af866-239">Geçerli uzmanlık belirleme koşulları</span><span class="sxs-lookup"><span data-stu-id="af866-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="af866-240">Adjoint/kontrollü işlem bildirimleri</span><span class="sxs-lookup"><span data-stu-id="af866-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="af866-241">Adjoint veya denetimli sürümleri olmayan bir işlem belirtmek için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="af866-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="af866-242">Örneğin, ölçüm işlemleri tersine çevrilebilir veya denetlenebilir olmadıkları için içermez.</span><span class="sxs-lookup"><span data-stu-id="af866-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="af866-243">Bir işlem, `Adjoint` `Controlled` bildirimi ilgili özelleştirmeler için örtük veya açık bir bildirim içeriyorsa, ve funları destekler.</span><span class="sxs-lookup"><span data-stu-id="af866-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="af866-244">Açıkça tanımlanmış bir adjoint/kontrollü özelleştirme, bir adjoint/denetimli özelleştirmenin varlığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="af866-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="af866-245">Gövdesi, yineleme-Until-başarılı döngüleri, set deyimlerini, ölçümleri, return deyimlerini veya funı desteklemeyen diğer işlemlere yapılan çağrıları içeren bir işlem için, `Adjoint` veya yönergesini izleyen bir adjoint özelleşmenin otomatik olarak oluşturulması `invert` `auto` mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="af866-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="af866-246">Gövdesi, functor desteklemeyen diğer işlemlere çağrı içeren bir işlem için `Controlled` , veya yönergesini izleyen denetimli bir özelleşmenin otomatik olarak oluşturulması `distribute` `auto` mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="af866-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="af866-247">Kontrollü adjoint</span><span class="sxs-lookup"><span data-stu-id="af866-247">Controlled Adjoint</span></span>

<span data-ttu-id="af866-248">Bir işlemin kontrollü adjoint sürümü, işlemin adjoint öğesinin hisse kontrollü bir sürümünün nasıl uygulanacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="af866-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="af866-249">Denetlenen adjoint sürümü olmayan bir işlem belirtmek için geçerlidir; Örneğin, ölçüm işlemlerinde denetlenebilir veya ters çevrilebilir olmadıkları için denetimli bir adjoint sürümü yoktur.</span><span class="sxs-lookup"><span data-stu-id="af866-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="af866-250">Bir işlem için denetimli bir adjoint özelleştirmesi, ve yalnızca bir adjoint ve denetimli bir özelleştirme varsa var olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="af866-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="af866-251">Bu durumda, denetlenen adjoint özelleşmenin varlığı algılanır.</span><span class="sxs-lookup"><span data-stu-id="af866-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="af866-252">Açıkça tanımlanmış bir uygulama yoksa, derleme uygun bir özelleştirme oluşturur.</span><span class="sxs-lookup"><span data-stu-id="af866-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="af866-253">Gövdesi denetimli bir adjoint sürümüne sahip olmayan diğer işlemlere çağrı içeren bir işlem için,, veya yönergesini izleyen bir adjoint özelleşmenin otomatik olarak oluşturulması `invert` `distribute` `auto` mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="af866-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="af866-254">Tür uyumluluğu</span><span class="sxs-lookup"><span data-stu-id="af866-254">Type Compatibility</span></span>

<span data-ttu-id="af866-255">Daha az komik, ancak aynı imzaya sahip bir işlem kullandığınızda her yerde desteklenen ek komik bir işlem kullanın.</span><span class="sxs-lookup"><span data-stu-id="af866-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="af866-256">Örneğin, türündeki bir işlemi kullandığınız her yerde türünde bir işlem kullanın `(Qubit => Unit is Adj)` `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="af866-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="af866-257">Q #, çağrılabilir dönüş türlerine göre *birlikte değişken* : bir tür döndüren çağrılabilir, `'A` aynı giriş türüne ve ile uyumlu bir sonuç türüne sahip çağrılabilir ile uyumludur `'A` .</span><span class="sxs-lookup"><span data-stu-id="af866-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="af866-258">S #, giriş türlerine göre *değişken karşıtı:* giriş olarak bir türü alan çağrılabilir, `'A` aynı sonuç türü ve ile uyumlu bir giriş türü olan çağrılabilir ile uyumludur `'A` .</span><span class="sxs-lookup"><span data-stu-id="af866-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="af866-259">Diğer bir deyişle, aşağıdaki tanımlar verildiğinde,</span><span class="sxs-lookup"><span data-stu-id="af866-259">That is, given the following definitions,</span></span>

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

<span data-ttu-id="af866-260">Şunları yapabilirsiniz</span><span class="sxs-lookup"><span data-stu-id="af866-260">you can</span></span>

- <span data-ttu-id="af866-261">`ConjugateInvertWith` `inner` Ya da bağımsız değişkeniyle işlevi çağırın `Invert` `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="af866-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="af866-262">İşlevi `ConjugateUnitaryWith` bir `inner` bağımsız değişkeniyle çağırın `ApplyUnitary` , ancak not edin `Invert` .</span><span class="sxs-lookup"><span data-stu-id="af866-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="af866-263">Türünden bir değer döndürür `(Qubit[] => Unit is Adj + Ctl)` `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="af866-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af866-264">Q # 0,3, Kullanıcı tanımlı türlerin davranışında önemli bir farklılık sunmuştur.</span><span class="sxs-lookup"><span data-stu-id="af866-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="af866-265">Kullanıcı tanımlı türler, alt tür yerine temel alınan türün Sarmalanan bir sürümü olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="af866-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="af866-266">Bu, Kullanıcı tanımlı türün bir değerinin, temel alınan türün bir değerini beklediğinizi tahmin ettiğiniz durumlarda kullanılabilir olmadığı anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="af866-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


### <a name="conjugations"></a><span data-ttu-id="af866-267">Conjugations</span><span class="sxs-lookup"><span data-stu-id="af866-267">Conjugations</span></span>

<span data-ttu-id="af866-268">Klasik bitlerin aksine, qubits 'in hala bir daha açık olması durumunda qubits 'in kalan hesaplamada istenmeyen etkileri olabildiğinden, hisse bitlerinin serbest bırakılması biraz daha karmaşıktır.</span><span class="sxs-lookup"><span data-stu-id="af866-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="af866-269">Belleği serbest bırakmadan önce, bu etkileri doğru "geri alma" sırasında gerçekleştirilen hesaplamaları önlenebilir.</span><span class="sxs-lookup"><span data-stu-id="af866-269">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="af866-270">Bu nedenle, hisse kullanımı için genel bir model aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="af866-270">A common pattern in quantum computing is hence the following:</span></span> 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

<span data-ttu-id="af866-271">0,9 sürümümüzden başlayarak, Q #, önceki dönüştürmeyi uygulayan bir Birleşik bildirim bildirisini destekler.</span><span class="sxs-lookup"><span data-stu-id="af866-271">Starting with our 0.9 release, Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="af866-272">Bu ifadeyi kullanarak, işlem `ApplyWith` aşağıdaki şekilde uygulanabilir:</span><span class="sxs-lookup"><span data-stu-id="af866-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
<span data-ttu-id="af866-273">Bu tür bir birleşim deyimi, dış ve iç dönüşümler işlem olarak hazır değilse ancak birkaç deyimden oluşan bir blok tarafından daha kolay tanımlanmıyorsa daha kullanışlı hale gelir.</span><span class="sxs-lookup"><span data-stu-id="af866-273">Such a conjugation statement becomes far more useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="af866-274">İçindeki blok içinde tanımlanan deyimler için ters dönüşüm, derleyici tarafından otomatik olarak oluşturulur ve Apply-Block tamamlandıktan sonra çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="af866-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="af866-275">İçindeki blok içinde kullanılan herhangi bir değişebilir değişken, Apply-Block içinde yeniden bağlanamaz, oluşturulan dönüşümün, hesaplamanın içindeki adeklik olduğu garanti edilir.</span><span class="sxs-lookup"><span data-stu-id="af866-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="af866-276">Yeni Işlevleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="af866-276">Defining New Functions</span></span>

<span data-ttu-id="af866-277">İşlevler, bir çıkış değerinin hesaplanmasının dışında etkileri olmasına izin verilmediğinden, işlemlerinden farklı olarak, yalnızca belirleyici olan, bu işlemler olan Q # içindeki klasik yordamlardır.</span><span class="sxs-lookup"><span data-stu-id="af866-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="af866-278">Özellikle, işlevler işlemleri çağıramaz; işlem yapın, ayırın veya ödünç alma; örnek rastgele sayılar; ya da diğer bir deyişle, giriş değerinin ötesine bir işleve bağımlı duruma bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="af866-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="af866-279">Sonuç olarak, Q # işlevleri *saf*olduğundan, her zaman aynı giriş değerlerini aynı çıkış değerleriyle eşleştirirler.</span><span class="sxs-lookup"><span data-stu-id="af866-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="af866-280">Bu davranış, Q # derleyicisinin, işlem uzmanlıklarını oluştururken işlevlerin nasıl ve ne zaman çağrılacağını güvenle yeniden oluşturmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="af866-280">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="af866-281">Her Q # kaynak dosyası herhangi bir sayıda işlev tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-281">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="af866-282">İşlev adları bir ad alanı içinde benzersiz olmalıdır ve işlem veya tür adlarıyla çakışamaz.</span><span class="sxs-lookup"><span data-stu-id="af866-282">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="af866-283">Bir işlev tanımlamak, bir işlev için hiçbir adjoint veya denetimli uzmanlık tanımlanmamasının dışında, bir işlemi tanımlamaya benzer şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="af866-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="af866-284">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="af866-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="af866-285">veya</span><span class="sxs-lookup"><span data-stu-id="af866-285">or</span></span> 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="af866-286">İşlevlerde klasik mantık = = iyi</span><span class="sxs-lookup"><span data-stu-id="af866-286">Classical logic in functions == good</span></span>

<span data-ttu-id="af866-287">Bunu yapmak mümkün olduğunda, işlemleri daha kolay kullanabilmek için işlemler yerine işlevler bakımından klasik mantığı yazmak yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="af866-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="af866-288">Örneğin, önceki `Square` bildirimi bir *işlem*olarak yazdıysanız, derleyici aynı girişe çağrı yapan aynı çıkışları tutarlı bir şekilde üretmesi gerektiğini garanti edemeyebilir.</span><span class="sxs-lookup"><span data-stu-id="af866-288">For example, if you had written the earlier `Square` declaration as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="af866-289">İşlevler ve işlemler arasındaki farkın altını bir şekilde çözmek için, bir Q # işlemi içinden rastgele bir sayı örnekleme sorununu ele alalım:</span><span class="sxs-lookup"><span data-stu-id="af866-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="af866-290">Her `U` çağrıldığında, üzerinde farklı bir eylem vardır `target` .</span><span class="sxs-lookup"><span data-stu-id="af866-290">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="af866-291">Özellikle, derleyici ' `adjoint auto` a bir özelleştirme bildirimi eklerseniz `U` , `U(target); Adjoint U(target);` kimlik olarak davranır (yani, işlem dışı).</span><span class="sxs-lookup"><span data-stu-id="af866-291">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="af866-292">Bu durum, [vektörlerin ve matrislerde](xref:microsoft.quantum.concepts.vectors)tanımlanan adekin tanımını ihlal eder, bu nedenle derleyicinin, işlemi çağırdığınız bir işlemde bir adjoint özelleşmesinin otomatik olarak oluşturmasını sağlayan bir işlem, <xref:microsoft.quantum.math.randomreal> derleyici tarafından sağlanmaları kesintiye uğratır; <xref:microsoft.quantum.math.randomreal> hiçbir adjoint veya kontrollü sürüm yok.</span><span class="sxs-lookup"><span data-stu-id="af866-292">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="af866-293">Öte yandan, gibi işlev çağrılarına izin verme `Square` ve derleyicinin `Square` çıktısının kalıcı kalmasını sağlamak için yalnızca girdiyi korumasının gerektiği konusunda bir değer sağlar.</span><span class="sxs-lookup"><span data-stu-id="af866-293">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="af866-294">Bu nedenle, işlevlerde mümkün olduğunca klasik mantığı yalıtmak, diğer işlevlerde ve işlemlerde bu mantığı yeniden kullanmayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="af866-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="af866-295">Genel (tür parametreli) Callables</span><span class="sxs-lookup"><span data-stu-id="af866-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="af866-296">Tanımlamak isteyebileceğiniz birçok işlev ve işlem, kendi giriş türlerine gerçekten büyük ölçüde güvenmiyor, ancak bunun yerine yalnızca başka bir işlev veya işlem aracılığıyla türlerini örtülü olarak kullanın.</span><span class="sxs-lookup"><span data-stu-id="af866-296">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="af866-297">Örneğin, yaygın olarak kullanılan *harita* kavramını birçok işlevsel dilde değerlendirin. $f (x) $ işlevi ve $ \{ x_1, x_2, \noktalar, x_n $, Map bir değer koleksiyonu verildiğinde, \} $ \{ f (x_1), f (x_2), \noktalar, f (x_n) $ gibi yeni bir koleksiyon döndürür \} .</span><span class="sxs-lookup"><span data-stu-id="af866-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="af866-298">Bunu Q # ' da uygulamak için işlevlerin ilk sınıf olduğu olgunun avantajlarından yararlanın.</span><span class="sxs-lookup"><span data-stu-id="af866-298">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="af866-299">İşte `Map` , `T` ihtiyacınız olan türleri öğrenirken yer tutucu olarak kullanmanın hızlı bir örneği.</span><span class="sxs-lookup"><span data-stu-id="af866-299">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="af866-300">Bu işlevin, hangi gerçek türleri Beğendiğinize bakılmaksızın çok fazla göründüğünü unutmayın.</span><span class="sxs-lookup"><span data-stu-id="af866-300">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="af866-301">Örneğin, tamsayılardan Paulis 'e yapılan bir harita, kayan noktalı sayıların dizelerdeki eşlemesiyle çok benzer şekilde görünür:</span><span class="sxs-lookup"><span data-stu-id="af866-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="af866-302">İlke ' de, `Map` karşılaştığınız her tür çifti için bir sürümü yazabilirsiniz, ancak bu çok sayıda zorluklar ortaya koymaktadır.</span><span class="sxs-lookup"><span data-stu-id="af866-302">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="af866-303">Örneğin, içinde bir hata bulursanız `Map` , düzeltmesinin tüm sürümlerinde bir şekilde uygulandığından emin olmanız gerekir `Map` .</span><span class="sxs-lookup"><span data-stu-id="af866-303">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="af866-304">Ayrıca, yeni bir tanımlama grubu veya UDT oluşturursanız, yeni türle birlikte yeni bir kayıt da oluşturmanız gerekir `Map` .</span><span class="sxs-lookup"><span data-stu-id="af866-304">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="af866-305">Bu, az sayıda işlev için daha fazla ve daha fazla işlev topladıkça, bu tür bir izleme tablosu olsa da `Map` , yeni türleri tanıtma maliyeti oldukça kısa bir süre boyunca makul bir şekilde büyük olur.</span><span class="sxs-lookup"><span data-stu-id="af866-305">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="af866-306">Bununla birlikte, bu zorluklar, derleyicinin farklı sürümlerinin nasıl ilişkili olduğunu tanıması için ihtiyaç duymamanızdan kaynaklanır `Map` .</span><span class="sxs-lookup"><span data-stu-id="af866-306">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="af866-307">Etkin olarak, derleyicinin `Map` bir tür matematik işlevi olarak q # *türünden* q # işlevlerine işlem görmesini istiyorsunuz.</span><span class="sxs-lookup"><span data-stu-id="af866-307">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="af866-308">S # formbu kavramı, işlevlerin ve işlemlerin *tür parametrelerine*ve bunların normal demet parametrelerine sahip olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="af866-308">Q# formalizes this notion by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="af866-309">Önceki örneklerde, `Map` `Int, Pauli` ilk durumda ve ikinci durumda tür parametrelerine sahip olacak şekilde düşünmek istersiniz `Double, String` .</span><span class="sxs-lookup"><span data-stu-id="af866-309">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="af866-310">Çoğu bölüm için, bu tür parametrelerini sıradan türlermiş gibi kullanın.</span><span class="sxs-lookup"><span data-stu-id="af866-310">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="af866-311">Dizi ve tanımlama oluşturmak, işlevleri ve işlemleri çağırmak ve sıradan ya da kesilebilir değişkenlere atamak için parametre türü değerlerini kullanın.</span><span class="sxs-lookup"><span data-stu-id="af866-311">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="af866-312">Dolaylı bağımlıların en büyük olması, bir Q # programının türün yapısına doğrudan güvenebileceği `Qubit` ancak bu tür türleri diğer işlemlere ve işlevlere geçirmesi **gereken** qubitlerdir.</span><span class="sxs-lookup"><span data-stu-id="af866-312">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="af866-313">Önceki örneğe dönerek, `Map` bir tane olmak üzere tür parametrelerine sahip olması gerektiğini, diğeri girişi temsil etmek için `fn` ise çıktıyı temsil edecek şekilde görürsünüz `fn` .</span><span class="sxs-lookup"><span data-stu-id="af866-313">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="af866-314">Q # dilinde, bu, `<>` {} bildiriminde bir işlev veya işlemin adından sonra ve her tür parametresini listeleyerek açılı ayraçlar (brakets $ \braket $! değil) eklenerek yazılır.</span><span class="sxs-lookup"><span data-stu-id="af866-314">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="af866-315">Her tür parametresinin adı bir Tick ile başlamalı `'` ve sıradan bir tür ( *somut* tür olarak da bilinir) değil bir tür parametresi olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="af866-315">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="af866-316">Bu nedenle, `Map` yazılır:</span><span class="sxs-lookup"><span data-stu-id="af866-316">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="af866-317">Tanımının `Map<'Input, 'Output>` previoius sürümlerine çok benzer şekilde göründüğünü unutmayın.</span><span class="sxs-lookup"><span data-stu-id="af866-317">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="af866-318">Tek fark, derleyiciye doğrudan bağlı olmayan ve ne olduğunu açıkça bildirdiğinize `Map` `'Input` `'Output` , ancak bunları dolaylı olarak aracılığıyla kullanarak her iki tür için de işe yarar `fn` .</span><span class="sxs-lookup"><span data-stu-id="af866-318">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="af866-319">Bu şekilde tanımladıktan sonra `Map<'Input, 'Output>` , normal bir fonksiyonmuş gibi çağırabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="af866-319">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="af866-320">Genel işlevler ve işlemler yazmak, "kayıt düzeni-Out" ın Q # işlevleri ve işlemlerini düşünmek için çok faydalı bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="af866-320">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="af866-321">Her işlev tam olarak bir giriş yaptığından ve tam olarak bir çıkış döndürdüğünden, türünde bir giriş `'T -> 'U` *herhangi* bir Q # işleviyle eşleşir.</span><span class="sxs-lookup"><span data-stu-id="af866-321">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="af866-322">Benzer şekilde, herhangi bir işlemi türü bir girişe geçirebilirsiniz `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="af866-322">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="af866-323">İkinci bir örnek olarak, iki diğer işlevin birleşimini döndüren bir işlev yazma sınamasını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="af866-323">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="af866-324">Burada, tam olarak ne `A` , `B` ve olduğunu belirtmeniz gerekir `C` . bu nedenle, yeni işlevimizin yardımcı programını ciddi ölçüde sınırlandırırsınız `Compose` .</span><span class="sxs-lookup"><span data-stu-id="af866-324">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="af866-325">All,,, ve ile `Compose` bağlıdır `A` `B` `C` *via* `innerFn` `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="af866-325">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="af866-326">Alternatif olarak,,, `Compose` ve için çalıştığını göstermek üzere tür parametreleri ekleyebilirsiniz *any* `A` `B` `C` ve bu parametrelerin, ve tarafından beklenenlerle eşleştiği sürece `innerFn` `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="af866-326">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="af866-327">Q # standart kitaplıkları, daha yüksek sıralı denetim akışı hızlı bir şekilde daha kolay hale getirmek için tür parametreli işlem ve işlev aralığı sağlar.</span><span class="sxs-lookup"><span data-stu-id="af866-327">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="af866-328">Bunlar, [Q # standart kitaplığı kılavuzunda](xref:microsoft.quantum.libraries.standard.intro)daha ayrıntılı olarak ele alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="af866-328">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="af866-329">Ilk sınıf değerleri olarak callables</span><span class="sxs-lookup"><span data-stu-id="af866-329">Callables as First-Class Values</span></span>

<span data-ttu-id="af866-330">İşlemler yerine işlevleri kullanarak denetim akışı ve klasik mantık hakkında önemli bir tekniktir, bu işlemler ve Q # içindeki işlevler *birinci sınıf*olur.</span><span class="sxs-lookup"><span data-stu-id="af866-330">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="af866-331">Diğer bir deyişle, her bir değer kendi sağ tarafındaki dilde değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="af866-331">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="af866-332">Örneğin, daha az dolaylı bir değer varsa, aşağıdakiler mükemmel bir Q # kodudur:</span><span class="sxs-lookup"><span data-stu-id="af866-332">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="af866-333">`ourH`Önceki kod parçacığında değişkenin değeri, daha sonra <xref:microsoft.quantum.intrinsic.h> Bu değeri diğer tüm işlemler gibi çağırabilmeniz için işlem olur.</span><span class="sxs-lookup"><span data-stu-id="af866-333">The value of the variable `ourH` in the previous snippet is then the operation <xref:microsoft.quantum.intrinsic.h>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="af866-334">Bu özellik sayesinde, işlemleri girişin bir parçası olarak alan ve daha yüksek sıralı denetim akışı kavramları oluşturan işlemler yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af866-334">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="af866-335">Örneğin, aynı hedef qubit 'e iki kez uygulayarak bir işlemi "kare" olarak düşünün.</span><span class="sxs-lookup"><span data-stu-id="af866-335">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="af866-336">İşlevden işlem döndürme</span><span class="sxs-lookup"><span data-stu-id="af866-336">Returning operations from a function</span></span>

<span data-ttu-id="af866-337">İşlemler, bir işlem biçiminde bir hisse programın açıklamasını döndüren klasik bir işlev olarak bazı klasik koşullu mantığı ayırabilmeniz için, işlemleri çıktıların bir parçası olarak de döndürebileceğinizi vurgulamanız önemlidir.</span><span class="sxs-lookup"><span data-stu-id="af866-337">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="af866-338">Basit bir örnek olarak, iki bitlik bir klasik ileti alan tarafın, bu iletiyi kullanarak doğru bir teleporm durumuna ulaşmasını sağlamak için ileti kullanması gereken teleporsyon örneğini düşünün.</span><span class="sxs-lookup"><span data-stu-id="af866-338">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="af866-339">Bunu, bu iki klasik biti alan ve uygun kod çözme işlemini döndüren bir işlev açısından yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af866-339">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

<span data-ttu-id="af866-340">Bu yeni işlev aslında bir işlevdir, ancak aynı değerleri ve ile çağırırsanız, `hereBit` `thereBit` her zaman aynı işlemi geri alırsınız.</span><span class="sxs-lookup"><span data-stu-id="af866-340">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="af866-341">Bu nedenle, kod çözme mantığının farklı işlem özelleştirmelerinin tanımlarına nasıl etkileştiğini fark etmeden güvenli bir şekilde çalışabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-341">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="af866-342">Diğer bir deyişle, bir işlev içindeki klasik mantık yalıtılmış ve bu, derleyicinin işlev çağrısının, bir giriş korunduğu sürece Impunity ile yeniden sıralanacağını kabul edilebilir.</span><span class="sxs-lookup"><span data-stu-id="af866-342">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="af866-343">Kısmi uygulama</span><span class="sxs-lookup"><span data-stu-id="af866-343">Partial Application</span></span>

<span data-ttu-id="af866-344">*Kısmi uygulama*kullanarak işlem döndüren işlevlerle çok daha fazlasını yapabilirsiniz. Bu, bir işleve veya işleme girişin bir veya daha fazla bölümünü gerçekten çağırmadan bir veya daha fazla şekilde sağlarsınız.</span><span class="sxs-lookup"><span data-stu-id="af866-344">You can do significantly more with functions that return operations by using *partial application*, in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="af866-345">Önceki örnekte, `ApplyTwice` giriş işleminin hangi qubit 'e uygulanacağını belirtmek istediğinizi belirtmek istemezsiniz:</span><span class="sxs-lookup"><span data-stu-id="af866-345">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="af866-346">Bu durumda, yerel değişken `twiceOp` kısmen uygulanan işlemi tutar; `ApplyTwice(op, _)` burada, `_` girişin henüz belirtilmediği bölümleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="af866-346">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="af866-347">`twiceOp`Sonraki satırda çağırdığınızda girişin geri kalan bölümlerinin tümü için kısmen uygulanmış işleme giriş olarak geçiş yapılır.</span><span class="sxs-lookup"><span data-stu-id="af866-347">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="af866-348">Bu nedenle, önceki kod parçacığı, doğrudan çağrılmasıyla aynı şekilde, `ApplyTwice(op, target)` Yeni bir yerel değişken sunmuş olduğunuz için kaydedin, böylece girişin bazı parçalarını sağlarken çağrıyı erteleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af866-348">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="af866-349">Kısmen uygulanmış bir işlem, tüm giriş sağlanana kadar gerçekten çağrılmadığı için, işlevleri içinden bile işlemleri güvenle uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="af866-349">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="af866-350">Prensibi, içindeki klasik mantık çok `SquareOperation` daha fazla olabilir, ancak derleyicinin işlevler hakkında sunabileceği garantilere göre bir işlemin geri kalanından yalıtılmıştır.</span><span class="sxs-lookup"><span data-stu-id="af866-350">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="af866-351">Q # standart kitaplığı, bu yaklaşımı, klasik denetim akışını, hisse uygun maliyetli bir şekilde ifade etmek için kullanır.</span><span class="sxs-lookup"><span data-stu-id="af866-351">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="af866-352">Özyineleme</span><span class="sxs-lookup"><span data-stu-id="af866-352">Recursion</span></span>

<span data-ttu-id="af866-353">Q # callables 'in doğrudan veya dolaylı olarak özyinelemeli olmasına izin verilir.</span><span class="sxs-lookup"><span data-stu-id="af866-353">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="af866-354">Diğer bir deyişle, bir işlem veya işlev kendisini çağırabilir veya çağrılabilir işlemi doğrudan veya dolaylı olarak çağıran başka bir çağrılabilir çağrısı yapabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-354">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="af866-355">Ancak özyineleme kullanımı hakkında iki önemli yorum vardır:</span><span class="sxs-lookup"><span data-stu-id="af866-355">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="af866-356">İşlemlerde özyineleme kullanımı, bazı iyileştirmelere engel olabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-356">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="af866-357">Bu girişim, algoritmanın yürütme süresi üzerinde önemli bir etkiye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-357">This interference can have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="af866-358">Gerçek bir hisse cihazında çalışırken yığın alanı sınırlı olabilir ve bu nedenle derin özyineleme bir çalışma zamanı hatasına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="af866-358">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="af866-359">Özellikle, Q # derleyicisi ve çalışma zamanı, kuyruk özyinelemeyi tanımlamaz ve iyileştirmez.</span><span class="sxs-lookup"><span data-stu-id="af866-359">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="af866-360">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="af866-360">Next steps</span></span>

<span data-ttu-id="af866-361">Q # [değişkenleri](xref:microsoft.quantum.guide.variables) hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="af866-361">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>