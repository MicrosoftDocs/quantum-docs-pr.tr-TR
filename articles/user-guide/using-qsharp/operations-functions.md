---
title: "Q 'daki işlemler ve işlevler #"
description: İşlem ve işlevlerin yanı sıra denetlenen ve Adjoint işlem uzmanlıklarını tanımlama ve çağırma.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 9e924b973c4f22a59dd862df3f4f0d70278a1b4e
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327807"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="4632d-103">Q 'daki işlemler ve Işlevler #</span><span class="sxs-lookup"><span data-stu-id="4632d-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="4632d-104">Yeni Işlemleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="4632d-104">Defining New Operations</span></span>

<span data-ttu-id="4632d-105">İşlemler, Q # ' ın temel sayısıdır.</span><span class="sxs-lookup"><span data-stu-id="4632d-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="4632d-106">Bildirdikten sonra, bir simülatör kullanılarak veya Q # içindeki diğer işlemler tarafından klasik .NET uygulamalarından çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="4632d-107">Q # içinde tanımlanan her işlem, dil tarafından tanımlanan yerleşik iç işlemler de dahil olmak üzere herhangi bir sayıda işlemi çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="4632d-108">Bu iç işlemlerin tanımlandığı belirli yol, hedef makineye bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="4632d-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="4632d-109">Derlendiğinde, her işlem hedef makinelere sağlanlenebilecek bir .NET sınıf türü olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="4632d-110">Her Q # kaynak dosyası herhangi bir sayıda işlem tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="4632d-111">İşlem adları ad alanı içinde benzersiz olmalıdır ve tür veya işlev adlarıyla çakışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="4632d-112">İşlem bildirimi, anahtar sözcüğünden ve `operation` ardından işlemin adı olan sembol, işlem için bağımsız değişkenleri tanımlayan türü belirlenmiş bir tanımlayıcı tanımlama grubu, iki nokta üst üste `:` , işlemin sonuç türünü açıklayan bir tür ek açıklaması, isteğe bağlı olarak işlem özelliklerine sahip bir ek açıklama, bir açık küme ayracı `{` , işlem bildiriminin gövdesi ve son kapanış ayracı oluşur `}` .</span><span class="sxs-lookup"><span data-stu-id="4632d-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="4632d-113">Her işlem bir girdi alır, bir çıktı üretir ve bir veya daha fazla işlem uzmanlığını için uygulamayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="4632d-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="4632d-114">Olası Uzmanlıklar ve bunların nasıl tanımlanacağı/çağrılacağını aşağıda bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4632d-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="4632d-115">Şimdilik yalnızca bir varsayılan gövde özelleştirmesi tanımlayan ve giriş olarak tek bir qubit alan aşağıdaki işlemi göz önünde bulundurun ve sonra <xref:microsoft.quantum.intrinsic.x> Bu girişte yerleşik işlemi çağırır:</span><span class="sxs-lookup"><span data-stu-id="4632d-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="4632d-116">Anahtar sözcüğü `operation` işlem tanımını başlatır ve ardından ad, burada, `BitFlip` .</span><span class="sxs-lookup"><span data-stu-id="4632d-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="4632d-117">Sonra, girişin türü `Qubit` , `target` Yeni işlemdeki girişe başvurmak için bir adla birlikte tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="4632d-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="4632d-118">Benzer şekilde, `Unit` işlem çıkışının boş olduğunu tanımlar.</span><span class="sxs-lookup"><span data-stu-id="4632d-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="4632d-119">Bu, `void` C# ve diğer zorunlu dillerde aynı şekilde kullanılır ve `unit` F # ve diğer işlevsel dillerde eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="4632d-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="4632d-120">İşlemler Ayrıca, öğesinden daha ilginç türler de döndürebilir `Unit` .</span><span class="sxs-lookup"><span data-stu-id="4632d-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="4632d-121">Örneğin, işlem, <xref:microsoft.quantum.intrinsic.m> `Result` ölçüm gerçekleştirmemiş olduğunu temsil eden türünde bir çıktı döndürür.</span><span class="sxs-lookup"><span data-stu-id="4632d-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="4632d-122">Bir işlemden çıkışı başka bir işleme geçirebiliriz ya da `let` Yeni bir değişken tanımlamak için anahtar sözcükle birlikte kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4632d-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="4632d-123">Bu, [yoğun kodlama](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)gibi düşük bir düzeyde hisse uygun olan klasik hesaplamayı temsil etmenizi sağlar:</span><span class="sxs-lookup"><span data-stu-id="4632d-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="4632d-124">Q # içindeki her işlem tam olarak bir giriş alır ve tam olarak bir çıkış döndürür.</span><span class="sxs-lookup"><span data-stu-id="4632d-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="4632d-125">Birden çok giriş ve çıkış daha sonra birden çok değeri tek bir değerde toplamak için *Tanımlama grupları*kullanılarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="4632d-126">Bu durumda, Q # ' ın bir "demet oluşturma" dili olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="4632d-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="4632d-127">Bu kavram sonrasında, `()` türü olan "boş" kayıt düzeni olarak okunmalıdır `Unit` .</span><span class="sxs-lookup"><span data-stu-id="4632d-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="4632d-128">Denetlenen ve Adjoint Işlemleri</span><span class="sxs-lookup"><span data-stu-id="4632d-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="4632d-129">Bir işlem, bir Unitary dönüştürmesi uygularsa, Q # içindeki birçok işlem için durum olduğu gibi, *adjointed* veya *denetimli*olduğunda işlemin nasıl davrandığını tanımlamak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="4632d-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="4632d-130">Bir işlemin *adjoint* özelleştirmesi işlemin nasıl davranması gerektiğini belirtir, *denetimli* bir özelleşme, uygulamanın belirli bir hisse kaydı durumunda olduğu durumlarda bir işlemin nasıl davranması gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="4632d-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="4632d-131">Hisse unsurlarının bir bölümünü, hisse bilgi işlem işlemlerinin birçok yönü için çok önemlidir.</span><span class="sxs-lookup"><span data-stu-id="4632d-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="4632d-132">Aşağıda, [conjugations](#conjugations) bölümünde, yararlı bir Q # programlama tekniğinin yanı sıra ele alınan bir durum bulacaksınız.</span><span class="sxs-lookup"><span data-stu-id="4632d-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="4632d-133">Bir işlemin denetlenen sürümü, yalnızca tüm denetim qubits 'in belirtilen durumda olması durumunda temel işlemi etkili bir şekilde uygulayan yeni bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="4632d-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="4632d-134">Denetim qubitleri üst konumundayken, temel işlem üst konumun uygun bölümüne doğru şekilde uygulanır.</span><span class="sxs-lookup"><span data-stu-id="4632d-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="4632d-135">Bu nedenle, denetimli işlemler genellikle entanglement oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4632d-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="4632d-136">Doğal olarak, *denetlenen bir adjoint* özelleştirmesi de bir işlemin adjoint öğesinin denetimli uygulamasını belirterek bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="4632d-137">$U $, bir işlem tarafından uygulanan Unitary dönüşümünde `U` , `Adjoint U` karmaşık eşleniği devrik olan "^ \dağılım $ $U Unitary dönüşümünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="4632d-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="4632d-138">Bir işlemin büyük bir bir şekilde uygulanması ve sonra adekliği, bu durum, $UU ^ \gger = U ^ \gger U = \ID $, kimlik matrisi olan olgu tarafından gösterildiği gibi durumu değişmeden bırakır.</span><span class="sxs-lookup"><span data-stu-id="4632d-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="4632d-139">Denetlenen bir işlemin Unitary temsili biraz daha fazla bir işlemdir, ancak daha fazla ayrıntı için [hisse bilgi işlem kavramlarıyla daha fazla bilgi bulabilirsiniz: birden çok qubit](xref:microsoft.quantum.concepts.multiple-qubits).</span><span class="sxs-lookup"><span data-stu-id="4632d-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="4632d-140">Aşağıdaki bölümde, bu çeşitli uzmanların Q # kodunuzda nasıl çağrılacağını açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="4632d-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="4632d-141">Aşağıda, bunları desteklemek için işlemlerin nasıl tanımlanacağı ayrıntılandırıyoruz.</span><span class="sxs-lookup"><span data-stu-id="4632d-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="4632d-142">İşlem uzmanlık işlemleri çağrılıyor</span><span class="sxs-lookup"><span data-stu-id="4632d-142">Calling operation specializations</span></span>

<span data-ttu-id="4632d-143">Q # ' daki bir *functor* , başka bir işlemden yeni bir işlem tanımlayan bir fabrikadır.</span><span class="sxs-lookup"><span data-stu-id="4632d-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="4632d-144">Q # içindeki iki standart komik `Adjoint` ve ' dir `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="4632d-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="4632d-145">Funörler, yeni işlemin uygulamasını tanımlarken temel işlemin uygulamasına erişebilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="4632d-146">Bu nedenle, funörler geleneksel daha yüksek düzey işlevlerden daha karmaşık işlevler gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="4632d-147">Funörler, Q # tür sisteminde bir gösterimine sahip değildir.</span><span class="sxs-lookup"><span data-stu-id="4632d-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="4632d-148">Bu nedenle, şu anda bunları bir değişkene bağlamak veya bağımsız değişken olarak geçirmek mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="4632d-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="4632d-149">Komik bir ctor, bir işleme uygulanarak yeni bir işlem döndürerek kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4632d-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="4632d-150">Örneğin, işlem için functor uygulamanın sonucu olan işlem `Adjoint` `Y` olarak yazılır `Adjoint Y` .</span><span class="sxs-lookup"><span data-stu-id="4632d-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="4632d-151">Yeni işlem daha sonra başka bir işlem gibi çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="4632d-152">Bir işlemin `Adjoint` ve/veya komik uygulamalarının uygulamasını desteklemesi için `Controlled` dönüş türünün olması gerekir `Unit` .</span><span class="sxs-lookup"><span data-stu-id="4632d-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="4632d-153">`Adjoint`functor</span><span class="sxs-lookup"><span data-stu-id="4632d-153">`Adjoint` functor</span></span>

<span data-ttu-id="4632d-154">Bu nedenle, `Adjoint Y(q1)` `Y` Yeni bir işlem oluşturmak Için adjoint functor işlemini uygular ve bu yeni işlemi öğesine uygular `q1` .</span><span class="sxs-lookup"><span data-stu-id="4632d-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="4632d-155">Yeni işlem, temel işlemle aynı imzaya ve türe sahip `Y` .</span><span class="sxs-lookup"><span data-stu-id="4632d-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="4632d-156">Özellikle, yeni işlem de izin verir `Adjoint` ve `Controlled` yalnızca temel işlem olduysa, ancak izin verir.</span><span class="sxs-lookup"><span data-stu-id="4632d-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="4632d-157">Adjoint functor kendi tersidir; Yani, `Adjoint Adjoint Op` her zaman ile aynıdır `Op` .</span><span class="sxs-lookup"><span data-stu-id="4632d-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="4632d-158">`Controlled`functor</span><span class="sxs-lookup"><span data-stu-id="4632d-158">`Controlled` functor</span></span>

<span data-ttu-id="4632d-159">Benzer şekilde, `Controlled X(controls, target)` `X` Yeni bir işlem oluşturmak için denetimli functor işlemini uygular ve bu yeni işlemi ve için uygular `controls` `target` .</span><span class="sxs-lookup"><span data-stu-id="4632d-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="4632d-160">Q # ' da denetimli sürümler her zaman bir denetim qubit dizisini alır ve belirtilen durum her zaman denetim qubits 'in hesaplama ( `PauliZ` ) `One` durumunda, $ \gre$ ' da olması için gereklidir {1} .</span><span class="sxs-lookup"><span data-stu-id="4632d-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="4632d-161">Diğer durumlara dayalı olarak denetlemek, denetimli işlemden önce denetim qubits 'e uygun Unitary işlemini uygulayarak ve sonra, denetimli işlemden sonra Unitary işleminin evirimini uygulayarak elde edilebilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="4632d-162">Örneğin, `X` denetimli bir işlemden önce ve sonra bir işlemi bir denetim qubit uygulamak, `Zero` Bu qubit için ($ \ket $) durumunda işlemin denetimine neden olur {0} ; durum `H` üzerinde önce ve sonra bir işlemi uygulamak `PauliX` `One` , durum yerine Pauli X, $ \tus\mathrel{ {-} : =} (\tus- {0} \ket {1} )/\sqrt {2} $ `PauliZ` `One` olan-1 eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="4632d-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="4632d-163">Bir işlem ifadesi verildiğinde, yeni bir işlem ifadesi `Controlled` functor kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="4632d-164">Yeni işlemin imzası, özgün işlemin imzasını temel alır.</span><span class="sxs-lookup"><span data-stu-id="4632d-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="4632d-165">Sonuç türü aynıdır, ancak giriş türü, ilk öğe olarak denetim qubit dizisini ve ikinci öğe olarak orijinal işlemin bağımsız değişkenlerini tutan bir qubit dizisi olan iki kayıt türüdür.</span><span class="sxs-lookup"><span data-stu-id="4632d-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="4632d-166">Yeni işlem `Controlled` ' i destekler ve `Adjoint` yalnızca özgün işlem olduysa, ve yalnızca bunu destekler.</span><span class="sxs-lookup"><span data-stu-id="4632d-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="4632d-167">Özgün işlem yalnızca tek bir bağımsız değişken alıyorsa, bu durumda tek demet denklik, burada yürütmeye gelir.</span><span class="sxs-lookup"><span data-stu-id="4632d-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="4632d-168">Örneğin, `Controlled X` işlemin denetlenen sürümüdür `X` .</span><span class="sxs-lookup"><span data-stu-id="4632d-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="4632d-169">`X`türüne sahip `(Qubit => Unit is Adj + Ctl)` , `Controlled X` Bu nedenle türüne sahip `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` . tek kayıt düzeni denkliği nedeniyle bu, ile aynıdır `((Qubit[], Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4632d-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="4632d-170">Temel işlem birkaç bağımsız değişken alıyorsa, bu işlemin denetlenen sürümünün ilgili bağımsız değişkenlerini, bir tanımlama grubu içine dönüştürmek için parantez içine almayı unutmayın.</span><span class="sxs-lookup"><span data-stu-id="4632d-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="4632d-171">Örneğin, `Controlled Rz` işlemin denetlenen sürümüdür `Rz` .</span><span class="sxs-lookup"><span data-stu-id="4632d-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="4632d-172">`Rz`türüne sahip `((Double, Qubit) => Unit is Adj + Ctl)` , bu nedenle `Controlled Rz` türüne sahip `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="4632d-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="4632d-173">Bu nedenle, `Controlled Rz(controls, (0.1, target))` geçerli bir çağrısı olur `Controlled Rz` (etrafındaki ayraçları aklınızda bulunan `0.1, target` ).</span><span class="sxs-lookup"><span data-stu-id="4632d-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="4632d-174">Başka bir örnek olarak, `CNOT(control, target)` olarak uygulanabilir `Controlled X([control], target)` .</span><span class="sxs-lookup"><span data-stu-id="4632d-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="4632d-175">Bir hedef 2 denetim qubits (CCNOT) tarafından denetleniyorsa, ifadesini kullanabiliriz `Controlled X([control1, control2], target)` .</span><span class="sxs-lookup"><span data-stu-id="4632d-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="4632d-176">`Controlled`Ve `Adjoint` komik, ve uygulama arasında bir fark yoktur `Controlled Adjoint Op` `Adjoint Controlled Op` .</span><span class="sxs-lookup"><span data-stu-id="4632d-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="4632d-177">Denetlenen ve Adjoint uygulamalarını tanımlama</span><span class="sxs-lookup"><span data-stu-id="4632d-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="4632d-178">Yukarıdaki ilk işlem bildirimi örneklerinde, işlemler `BitFlip` ve `DecodeSuperdense` sırasıyla imzalar ve ile tanımlanmıştır `(Qubit => Unit)` `((Qubit, Qubit) => (Result, Result))` .</span><span class="sxs-lookup"><span data-stu-id="4632d-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="4632d-179">`DecodeSuperdense`Ölçümler de dahil olmak üzere, Unitary bir işlem değildir ve bu nedenle hiçbir adeksel uzmanlık yok (Bu, bu tür bir işlemin döndürdüğü ilgili gereksinimi geri çağırır `Unit` ).</span><span class="sxs-lookup"><span data-stu-id="4632d-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="4632d-180">Ancak, `BitFlip` yalnızca Unitary işlemini gerçekleştirdiğinden, <xref:microsoft.quantum.intrinsic.x> her iki uzmanlıklarla de tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="4632d-181">Burada, Q # işlem bildirimlerinizde uzmanlıkların nasıl ekleneceğini ayrıntılandırıyoruz ve bu nedenle, `Adjoint` ve/veya funlar ile birlikte çağrılabilir `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="4632d-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="4632d-182">[Aşağıda](#circumstances-for-validly-defining-specializations), geçerli olduğu veya belirli uzmanlık bildirmek için geçerli olmayan bazı durumlar açıklanır.</span><span class="sxs-lookup"><span data-stu-id="4632d-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="4632d-183">İşlem özellikleri, hangi tür nesnelerin beyan edilen işleme uygulanabileceğini ve sahip oldukları etkiyi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="4632d-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="4632d-184">Bu uzmanlıklardan biri, özellikle işlem özelliklerine sahip bir ek açıklama aracılığıyla işlem imzasının bir parçası olarak bildirilemez: `is Adj` ,, `is Ctl` veya `is Adj + Ctl` .</span><span class="sxs-lookup"><span data-stu-id="4632d-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="4632d-185">Her özelleştirmenin gerçek uygulama *örtük* veya *Açık* bir şekilde tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="4632d-186">Örtük olarak uygulamaları belirtme</span><span class="sxs-lookup"><span data-stu-id="4632d-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="4632d-187">Bu durumda, işlem bildiriminin gövdesi yalnızca varsayılan uygulamadan oluşur.</span><span class="sxs-lookup"><span data-stu-id="4632d-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="4632d-188">Örnek:</span><span class="sxs-lookup"><span data-stu-id="4632d-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="4632d-189">Burada, örtük olarak tanımlanmış her bir özelleştirme için karşılık gelen uygulama, veya komik kullanılıyorsa, derleyici tarafından otomatik olarak oluşturulur `Adjoint` `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="4632d-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="4632d-190">Bu nedenle, bir çağrısı `Adjoint PrepareEntangledPair` derleyicinin adekini `CNOT` ve sonra adekini uygulamasına neden olur `H` .</span><span class="sxs-lookup"><span data-stu-id="4632d-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="4632d-191">Bu bireysel işlemler kendi kendine adekdir, bu nedenle sonuçtaki `Adjoint PrepareEntangledPair` işlem yalnızca uygulama `CNOT(here, there)` ve ardından oluşur `H(here)` .</span><span class="sxs-lookup"><span data-stu-id="4632d-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="4632d-192">Bu nedenle `DecodeSuperdense` , `PrepareEntangledPair` entangled durumunu bir qubit çiftiyle geri dönüştürmek için adjoint öğesini kullanarak daha fazla sıkı örneğini yazmak için bunu kullanabiliriz:</span><span class="sxs-lookup"><span data-stu-id="4632d-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="4632d-193">Bildirimin işlem özellikleriyle birlikte ek açıklama, derleyicinin varsayılan uygulamaya göre diğer özelleştirmeleri otomatik olarak üretmesinin güvence altına almak için yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="4632d-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="4632d-194">Funlar ile kullanım için işlemleri tasarlarken göz önünde bulundurmanız gereken bazı önemli sınırlamalar vardır.</span><span class="sxs-lookup"><span data-stu-id="4632d-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="4632d-195">Aynı etkiyi elde etmek için bu tür bir işlemde deyimleri yeniden sıralamak belirsiz olduğundan, başka bir *işlemin çıkış* değerini kullanan bir işlem için en kritik öneme sahip olan uzmanlık, derleyici tarafından otomatik olarak üretilemez.</span><span class="sxs-lookup"><span data-stu-id="4632d-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="4632d-196">Bu nedenle, genellikle çeşitli uygulamaları açıkça belirtmek yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="4632d-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="4632d-197">Uygulamaları açıkça belirtme</span><span class="sxs-lookup"><span data-stu-id="4632d-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="4632d-198">Uygulamanın derleyici tarafından üretilebileceği durumda, açıkça belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="4632d-199">Bu tür açık özelleşmeler, uygun bir *oluşturma yönergesinin* veya Kullanıcı tanımlı bir uygulamadan oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="4632d-200">Burada aşağıda belirtilen örneklerle birlikte tam olarak çeşitli olanaklar sağlıyoruz.</span><span class="sxs-lookup"><span data-stu-id="4632d-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="4632d-201">Açık Özelleştirme bildirimleri</span><span class="sxs-lookup"><span data-stu-id="4632d-201">Explicit specialization declarations</span></span>

<span data-ttu-id="4632d-202">S # işlemleri aşağıdaki açık özelleştirme bildirimlerini içerebilir:</span><span class="sxs-lookup"><span data-stu-id="4632d-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="4632d-203">`body`Özelleşme, hiçbir komik uygulanmamış şekilde işlemin uygulanmasını belirtir.</span><span class="sxs-lookup"><span data-stu-id="4632d-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="4632d-204">`adjoint`Özelleşme, işlem için `Adjoint` functor uygulanmış olan uygulamayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="4632d-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="4632d-205">`controlled`Özelleşme, işlem için `Controlled` functor uygulanmış olan uygulamayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="4632d-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="4632d-206">`controlled adjoint`Özelleşme, hem hem de `Adjoint` funları uygulanan işlemin uygulanmasını belirtir `Controlled` .</span><span class="sxs-lookup"><span data-stu-id="4632d-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="4632d-207">Bu özelleşme `adjoint controlled` , iki komik bulunduğu için de adlandırılmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="4632d-208">Bir işlem özelleştirmesi, özelleştirme etiketinden (ör. `body` veya `adjoint` , vb.) sonra aşağıdakilerden birini içerir:</span><span class="sxs-lookup"><span data-stu-id="4632d-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="4632d-209">Aşağıda açıklandığı gibi açık bir bildirim.</span><span class="sxs-lookup"><span data-stu-id="4632d-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="4632d-210">Derleyiciye özelleştirmenin *nasıl* oluşturulacağını belirten bir *yönerge* , aşağıdakilerden biri:</span><span class="sxs-lookup"><span data-stu-id="4632d-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="4632d-211">`intrinsic`, özelleşmenin hedef makine tarafından sağlandığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="4632d-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="4632d-212">`distribute`, `controlled` ve `controlled adjoint` uzmanlarıyla kullanılabilecek.</span><span class="sxs-lookup"><span data-stu-id="4632d-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="4632d-213">İle kullanıldığında `controlled` , derleyicinin `Controlled` , içindeki tüm işlemlere uygulanarak özelleştirmeyi hesaplaması gerektiğini belirtir `body` .</span><span class="sxs-lookup"><span data-stu-id="4632d-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="4632d-214">İle kullanıldığında `controlled adjoint` , derleyicinin özelleşmenin tüm işlemlerine uygulayarak özelleştirmeyi hesaplaması gerektiğini belirtir `Controlled` `adjoint` .</span><span class="sxs-lookup"><span data-stu-id="4632d-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="4632d-215">`invert`Bu, derleyicinin özelleştirmeyi hesaplaması gerektiğini gösterir, `adjoint` `body` Örneğin, işlem sırasını tersine çevirme ve her birine adeki uygulama.</span><span class="sxs-lookup"><span data-stu-id="4632d-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="4632d-216">İle kullanıldığında `adjoint controlled` , bu, derleyicinin özelleştirmeyi ters çeviren şekilde özelleşmesi gerektiğini belirtir `controlled` .</span><span class="sxs-lookup"><span data-stu-id="4632d-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="4632d-217">`self`, adjoint özelleşmenin özelleşme ile aynı olduğunu göstermek için `body` .</span><span class="sxs-lookup"><span data-stu-id="4632d-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="4632d-218">Bu, `adjoint` ve `adjoint controlled` Uzmanlıklar için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="4632d-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="4632d-219">İçin `adjoint controlled` , `self` `adjoint controlled` özelleştirmenin özelleştirme ile aynı olduğunu gösterir `controlled` .</span><span class="sxs-lookup"><span data-stu-id="4632d-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="4632d-220">`auto`, derleyicinin uygulanacak uygun bir yönergeyi seçmesini belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="4632d-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="4632d-221">`auto``body`özelleşme için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="4632d-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="4632d-222">Yönergelerin ve `auto` tümünün bir kapanış noktalı virgül olması gerekir `;` .</span><span class="sxs-lookup"><span data-stu-id="4632d-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="4632d-223">`auto`Yönergesi, bir açık bildirimi sağlanmışsa, aşağıdaki nesil yönergesini çözümler `body` :</span><span class="sxs-lookup"><span data-stu-id="4632d-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="4632d-224">`adjoint`Özelleşme, yönergeye göre oluşturulur `invert` .</span><span class="sxs-lookup"><span data-stu-id="4632d-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="4632d-225">`controlled`Özelleşme, yönergeye göre oluşturulur `distribute` .</span><span class="sxs-lookup"><span data-stu-id="4632d-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="4632d-226">`adjoint controlled` `invert` İçin açık bir bildirime izin `controlled` verilse `adjoint` , ve yoksa, özelleştirme yönergeye göre oluşturulur `distribute` .</span><span class="sxs-lookup"><span data-stu-id="4632d-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="4632d-227">Bir işlem kendi kendine adekiyiyise, `self` derleyicinin en iyi duruma getirme amacıyla bu bilgileri kullanmasına izin vermek için oluşturma yönergesi aracılığıyla adjoint veya denetimli adjoint özelleşmesini açıkça belirtin.</span><span class="sxs-lookup"><span data-stu-id="4632d-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="4632d-228">Kullanıcı tanımlı bir uygulama içeren bir özelleştirme bildirimi, bir bağımsız değişken kayıt kümesinden ve ardından, özelleştirmeyi uygulayan Q # koduna sahip bir ekstre bloğundan oluşur.</span><span class="sxs-lookup"><span data-stu-id="4632d-228">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="4632d-229">Bağımsız değişken listesinde, `...` işlem için belirtilen bağımsız değişkenleri bir bütün olarak temsil etmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="4632d-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="4632d-230">`body`Ve için `adjoint` bağımsız değişken listesi her zaman olmalıdır `(...)` ; ve için `controlled` `adjoint controlled` bağımsız değişken listesi, denetim qubits dizisini temsil eden bir sembol olmalıdır `...` ; Örneğin, parantez içine alınmış `(controls,...)` .</span><span class="sxs-lookup"><span data-stu-id="4632d-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="4632d-231">Örnekler</span><span class="sxs-lookup"><span data-stu-id="4632d-231">Examples</span></span>

<span data-ttu-id="4632d-232">İşlem bildirimi, temel Pauli X işlemini tanımlayan aşağıdaki kadar basit olabilir:</span><span class="sxs-lookup"><span data-stu-id="4632d-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="4632d-233">Pauli X işleminin adjoint değeri, `self` tanım tarafından kendi tersi olduğundan, yönergeyle tanımlandığını unutmayın `X` .</span><span class="sxs-lookup"><span data-stu-id="4632d-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="4632d-234">Örneğin, yukarıdaki kod, `PrepareEntangledPair` Açık özelleştirme bildirimlerini içeren aşağıdaki koda eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="4632d-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="4632d-235">Anahtar sözcüğü, `auto` derleyicinin nasıl özelleşdiğini uygulamanın nasıl oluşturulacağını belirlemesi gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="4632d-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="4632d-236">Kullanıcı tanımlı özelleştirme uygulama</span><span class="sxs-lookup"><span data-stu-id="4632d-236">User-defined specialization implementation</span></span>

<span data-ttu-id="4632d-237">Derleyici belirli bir özelleşmenin uygulamasını otomatik olarak üretemiyor veya daha verimli bir uygulama verilirse, uygulama da el ile tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
<span data-ttu-id="4632d-238">Yukarıdaki örnekte, `adjoint invert;` adjoint özelleşmesinin gövde uygulamasını tersine çeviren ve denetimli bir `controlled adjoint invert;` adjoint özelleşmesinin, denetlenen özelleşmenin belirtilen uygulamasını tersine ayırarak oluşturulacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="4632d-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="4632d-239">Varsayılan gövdenin yanı sıra bir veya daha fazla özelleştirilmiş açıkça bildirilmesi gerekiyorsa, varsayılan gövdeye yönelik uygulamanın uygun bir özelleştirme bildirimine de sarmalanması gerekir:</span><span class="sxs-lookup"><span data-stu-id="4632d-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="4632d-240">Geçerli uzmanlık belirleme koşulları</span><span class="sxs-lookup"><span data-stu-id="4632d-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="4632d-241">Adjoint/kontrollü işlem bildirimleri</span><span class="sxs-lookup"><span data-stu-id="4632d-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="4632d-242">Adjoint veya denetimli sürümleri olmayan bir işlem belirtmek için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="4632d-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="4632d-243">Örneğin, ölçüm işlemleri tersine çevrilebilir veya denetlenebilir olmadığından, bu işlemler değildir.</span><span class="sxs-lookup"><span data-stu-id="4632d-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="4632d-244">Bir işlem, `Adjoint` `Controlled` bildirimi ilgili özelleştirmeler için örtük veya açık bir bildirim içeriyorsa, ve/veya komik oluşturucuları destekler.</span><span class="sxs-lookup"><span data-stu-id="4632d-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="4632d-245">Açıkça tanımlanmış bir adjoint/kontrollü özelleştirme, bir adjoint/denetimli özelleştirmenin varlığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="4632d-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="4632d-246">Gövdesi, yineleme-Until-başarılı döngüleri, set deyimlerini, ölçümleri, return deyimlerini veya funı desteklemeyen diğer işlemlere yapılan çağrıları içeren bir işlem için, `Adjoint` veya yönergesini izleyen bir adjoint özelleşmenin otomatik olarak oluşturulması `invert` `auto` mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="4632d-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="4632d-247">Gövdesi, functor desteklemeyen diğer işlemlere çağrı içeren bir işlem için `Controlled` , veya yönergesini izleyen denetimli bir özelleşmenin otomatik olarak oluşturulması `distribute` `auto` mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="4632d-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="4632d-248">Kontrollü adjoint</span><span class="sxs-lookup"><span data-stu-id="4632d-248">Controlled Adjoint</span></span>

<span data-ttu-id="4632d-249">Bir işlemin kontrollü adjoint sürümü, işlemin adjoint öğesinin hisse kontrollü bir sürümünün nasıl uygulandığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="4632d-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="4632d-250">Denetlenen adjoint sürümü olmayan bir işlem belirtmek için geçerlidir; Örneğin, ölçüm işlemlerinde denetlenebilir veya ters çevrilebilir olmadıkları için denetimli bir adjoint sürümü yoktur.</span><span class="sxs-lookup"><span data-stu-id="4632d-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="4632d-251">Bir işlem için denetimli bir adjoint özelleştirmesi, ve yalnızca bir adjoint ve denetimli bir özelleştirme varsa var olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="4632d-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="4632d-252">Bu durumda, denetimli adjoint özelleşmenin varlığı algılanır ve hiçbir uygulama açıkça tanımlanmazsa derleyici tarafından uygun bir özelleştirme oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4632d-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="4632d-253">Gövdesi denetimli bir adjoint sürümüne sahip olmayan diğer işlemlere çağrı içeren bir işlem için, veya yönergesini izleyen bir adjoint özelleştirmesi otomatik olarak `invert` `distribute` `auto` oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="4632d-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="4632d-254">Tür uyumluluğu</span><span class="sxs-lookup"><span data-stu-id="4632d-254">Type Compatibility</span></span>

<span data-ttu-id="4632d-255">Desteklenen ek bir işlem, daha az komik olan bir işlemin her yerde kullanılabilir, ancak aynı imza beklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="4632d-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="4632d-256">Örneğin, türünde bir işlem `(Qubit => Unit is Adj)` beklenen her yerde kullanılabilir `(Qubit => Unit)` .</span><span class="sxs-lookup"><span data-stu-id="4632d-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="4632d-257">Q #, çağrılabilir dönüş türlerine göre *birlikte değişken* : bir tür döndüren çağrılabilir, `'A` aynı giriş türüne ve ile uyumlu bir sonuç türüne sahip çağrılabilir ile uyumludur `'A` .</span><span class="sxs-lookup"><span data-stu-id="4632d-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="4632d-258">S #, giriş türlerine göre *değişken karşıtı:* giriş olarak bir türü alan çağrılabilir, `'A` aynı sonuç türü ve ile uyumlu bir giriş türü olan çağrılabilir ile uyumludur `'A` .</span><span class="sxs-lookup"><span data-stu-id="4632d-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="4632d-259">Diğer bir deyişle, aşağıdaki tanımlar verilir:</span><span class="sxs-lookup"><span data-stu-id="4632d-259">That is, given the following definitions:</span></span>

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

<span data-ttu-id="4632d-260">aşağıdakiler doğrudur:</span><span class="sxs-lookup"><span data-stu-id="4632d-260">the following are true:</span></span>

- <span data-ttu-id="4632d-261">İşlev `ConjugateInvertWith` `inner` ya da veya bağımsız değişkeniyle çağrılabilir `Invert` `ApplyUnitary` .</span><span class="sxs-lookup"><span data-stu-id="4632d-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="4632d-262">İşlev `ConjugateUnitaryWith` `inner` , bağımsız değişkeniyle çağrılabilir `ApplyUnitary` , ancak değil `Invert` .</span><span class="sxs-lookup"><span data-stu-id="4632d-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="4632d-263">Türünde bir değer `(Qubit[] => Unit is Adj + Ctl)` döndürülebilecek `ConjugateInvertWith` .</span><span class="sxs-lookup"><span data-stu-id="4632d-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4632d-264">Q # 0,3, Kullanıcı tanımlı türlerin davranışında önemli bir farklılık sunmuştur.</span><span class="sxs-lookup"><span data-stu-id="4632d-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="4632d-265">Kullanıcı tanımlı türler, alt tür yerine temel alınan türün Sarmalanan bir sürümü olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="4632d-266">Bu, Kullanıcı tanımlı türün bir değerinin, temel alınan türden bir değerin beklenildiği durumlarda kullanılamaz olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="4632d-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="4632d-267">Conjugations</span><span class="sxs-lookup"><span data-stu-id="4632d-267">Conjugations</span></span>

<span data-ttu-id="4632d-268">Klasik bitlerin aksine, qubits 'in hala bir daha açık olması durumunda qubits 'in kalan hesaplamada istenmeyen etkileri olabildiğinden, hisse bitlerinin serbest bırakılması biraz daha karmaşıktır.</span><span class="sxs-lookup"><span data-stu-id="4632d-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="4632d-269">Bu, belleğin serbest bırakılmasından önce düzgün bir şekilde "geri alma" sırasında gerçekleştirilen hesaplamaları önlenebilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="4632d-270">Bu nedenle, hisse kullanımı için genel bir model aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="4632d-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="4632d-271">0,9 sürümümüzden başlayarak, yukarıdaki dönüşümü uygulayan bir Birleşik bildirim bildirisini destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="4632d-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="4632d-272">Bu ifadeyi kullanarak, işlem `ApplyWith` aşağıdaki şekilde uygulanabilir:</span><span class="sxs-lookup"><span data-stu-id="4632d-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="4632d-273">Bu tür bir birleşim deyimi, dış ve iç dönüşüm işlem olarak hazır değilse ancak birkaç deyimden oluşan bir blok tarafından tanımlanmakla daha kullanışlı hale gelirse çok daha yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="4632d-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="4632d-274">İçindeki blok içinde tanımlanan deyimler için ters dönüşüm, derleyici tarafından otomatik olarak oluşturulur ve Apply-Block tamamlandıktan sonra yürütülür.</span><span class="sxs-lookup"><span data-stu-id="4632d-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="4632d-275">İçindeki blok içinde kullanılan herhangi bir değişebilir değişken, Apply-Block içinde yeniden bağlanamaz, oluşturulan dönüşümün, hesaplamanın içindeki adeklik olduğu garanti edilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="4632d-276">Yeni Işlevleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="4632d-276">Defining New Functions</span></span>

<span data-ttu-id="4632d-277">İşlevler, bir çıkış değerinin hesaplanmasının dışında etkileri olmasına izin verilmediğinden, işlemlerinden farklı olarak, yalnızca belirleyici olan, bu işlemler olan Q # içindeki klasik yordamlardır.</span><span class="sxs-lookup"><span data-stu-id="4632d-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="4632d-278">Özellikle, işlevler işlemleri çağıramaz; işlem yapın, ayırın veya ödünç alma; örnek rastgele sayılar; ya da diğer bir deyişle, giriş değerinin ötesine bir işleve bağımlı duruma bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="4632d-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="4632d-279">Sonuç olarak, Q # işlevleri *saf*olduğundan, her zaman aynı giriş değerlerini aynı çıkış değerleriyle eşleştirirler.</span><span class="sxs-lookup"><span data-stu-id="4632d-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="4632d-280">Bu, Q # derleyicisinin, işlem uzmanlıklarını oluştururken işlevleri nasıl ve ne zaman çağırdığını güvenle yeniden sıralamak için izin verir.</span><span class="sxs-lookup"><span data-stu-id="4632d-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="4632d-281">Her Q # kaynak dosyası herhangi bir sayıda işlev tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="4632d-282">İşlev adları bir ad alanı içinde benzersiz olmalıdır ve işlem veya tür adlarıyla çakışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="4632d-283">Bir işlev tanımlamak, bir işlev için hiçbir adjoint veya denetimli uzmanlık tanımlanmamasının dışında, bir işlemi tanımlamaya benzer şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="4632d-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="4632d-284">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="4632d-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="4632d-285">veya</span><span class="sxs-lookup"><span data-stu-id="4632d-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="4632d-286">İşlevlerde klasik mantık = = iyi</span><span class="sxs-lookup"><span data-stu-id="4632d-286">Classical logic in functions == good</span></span>

<span data-ttu-id="4632d-287">Bunu yapmak mümkün olduğunda, işlemler içinden daha kolay bir şekilde kullanılabilmesi için klasik mantığı işlemler yerine işlevler bakımından yazmak yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="4632d-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="4632d-288">Örneğin, `Square` bir *işlem*olarak yukarıdaki bildirimi yazdığımızda, derleyici aynı girişe çağrı yapan aynı çıktıyı tutarlı bir şekilde ürettireceğinizin garanti edilemez.</span><span class="sxs-lookup"><span data-stu-id="4632d-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="4632d-289">İşlevler ve işlemler arasındaki farkın altını bir şekilde çözmek için, bir Q # işlemi içinden rastgele bir sayı örnekleme sorununu ele alalım:</span><span class="sxs-lookup"><span data-stu-id="4632d-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="4632d-290">Her `U` çağrıldığında, üzerinde farklı bir eylem olur `target` .</span><span class="sxs-lookup"><span data-stu-id="4632d-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="4632d-291">Özellikle, derleyici ' a bir özelleştirme bildirimi eklediğimiz ve `adjoint auto` `U` `U(target); Adjoint U(target);` kimlik olarak (yani, işlem dışı) hareket ettiğimiz konusunda garanti edemez.</span><span class="sxs-lookup"><span data-stu-id="4632d-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="4632d-292">Bu, [vektörlerin ve matrislerde](xref:microsoft.quantum.concepts.vectors)gördüğdiğimiz adjoint 'in tanımını ihlal ediyor. bu nedenle, işlemi çağırdığımız bir işlemde bir adjoint özelleştirmesi otomatik olarak oluşturmaya izin veren bir işlem, <xref:microsoft.quantum.math.randomreal> derleyici tarafından verilen garantileri bozacağı, <xref:microsoft.quantum.math.randomreal> hiçbir adjoint veya kontrollü sürüm yok.</span><span class="sxs-lookup"><span data-stu-id="4632d-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="4632d-293">Öte yandan, bu gibi işlev çağrılarına güvenli bir şekilde izin vermek `Square` , derleyicinin `Square` çıktısının kalıcı tutulmasını sağlamak için yalnızca girişi korumasının gerektiği konusunda emin olabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="4632d-294">Bu nedenle, işlevlerde mümkün olduğunca klasik mantığı yalıtmak, diğer işlevlerde ve işlemlerde bu mantığı yeniden kullanmayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="4632d-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="4632d-295">Genel (tür parametreli) Callables</span><span class="sxs-lookup"><span data-stu-id="4632d-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="4632d-296">Tanımlamak isteyebileceğiniz birçok işlev ve işlem, kendi giriş türlerine gerçekten büyük ölçüde güvenmiyor, ancak bunun yerine yalnızca başka bir işlev veya işlem aracılığıyla türlerini örtülü olarak kullanın.</span><span class="sxs-lookup"><span data-stu-id="4632d-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="4632d-297">Örneğin, yaygın olarak kullanılan *harita* kavramını birçok işlevsel dilde değerlendirin. $f (x) $ işlevi ve $ \{ x_1, x_2, \noktalar, x_n $, Map bir değer koleksiyonu verildiğinde, \} $ \{ f (x_1), f (x_2), \noktalar, f (x_n) $ gibi yeni bir koleksiyon döndürür \} .</span><span class="sxs-lookup"><span data-stu-id="4632d-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="4632d-298">Bunu Q # ' da uygulamak için, bu işlevlerden faydalanabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="4632d-299">`Map`İhtiyaç duyduğumuz türleri öğrenirken ★ bir yer tutucu olarak kullanarak hızlı bir örnek yazalım.</span><span class="sxs-lookup"><span data-stu-id="4632d-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="4632d-300">Bu işlev, yaptığımız gerçek türler dikkate alınmaz.</span><span class="sxs-lookup"><span data-stu-id="4632d-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="4632d-301">Örneğin, tamsayılardan Paulis 'e yapılan bir harita, kayan noktalı sayıların dizelerdeki eşlemesiyle çok benzer şekilde görünür:</span><span class="sxs-lookup"><span data-stu-id="4632d-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="4632d-302">Prensibi, `Map` Karşılaşdığımız her tür çifti için bir sürümü yazalım, ancak bu çok sayıda zorluklar sunarız.</span><span class="sxs-lookup"><span data-stu-id="4632d-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="4632d-303">Örneğin, içinde bir hata bulduk `Map` , bu durumda düzeltilmesinin tüm sürümlerinde bir şekilde uygulandığından emin olunması gerekir `Map` .</span><span class="sxs-lookup"><span data-stu-id="4632d-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="4632d-304">Ayrıca, yeni bir tanımlama grubu veya UDT oluşturuyoruz, yeni tür ile birlikte yeni bir kayıt da oluşturmanız gerekir `Map` .</span><span class="sxs-lookup"><span data-stu-id="4632d-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="4632d-305">Bu, çok sayıda işlev için daha fazla ve daha fazla işlev topladığımızda, bu, bu tür birkaç işlevi izlüyor olsa `Map` da, yeni türleri tanıtma maliyeti oldukça kısa bir sürede makul bir şekilde büyük olur.</span><span class="sxs-lookup"><span data-stu-id="4632d-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="4632d-306">Bununla birlikte, bu zorluk büyük bir bölümü, derleyicinin farklı sürümlerinin nasıl ilişkili olduğunu tanıması için ihtiyaç duymadığımızda oluşur `Map` .</span><span class="sxs-lookup"><span data-stu-id="4632d-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="4632d-307">Etkin olarak, derleyicinin `Map` bir tür matematik işlevi olarak q # *türünden* q # işlevlerine kadar davranmamasını istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="4632d-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="4632d-308">Bu kavram, işlevlerin ve işlemlerin *tür parametrelerine*ve bunların normal demet parametrelerine sahip olmasını sağlayarak şekillendirililir.</span><span class="sxs-lookup"><span data-stu-id="4632d-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="4632d-309">Yukarıdaki örneklerde, `Map` `Int, Pauli` ilk durumda ve ikinci durumda tür parametreleri varmış gibi düşünmek istiyoruz `Double, String` .</span><span class="sxs-lookup"><span data-stu-id="4632d-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="4632d-310">Çoğu bölüm için, bu tür parametreleri normal türlermiş gibi kullanılabilir: dizileri ve tanımlama grupları oluşturmak, işlevleri ve işlemleri çağırmak ve sıradan ya da kesilebilir değişkenlere atamak için parametre türü değerlerini kullanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="4632d-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="4632d-311">Dolaylı bağımlıların en büyük olması, bir Q # programının doğrudan türün yapısına bağlı olması `Qubit` ve bu tür türleri diğer işlemlere ve işlevlere geçirmesi **gereken** qubitlerdir.</span><span class="sxs-lookup"><span data-stu-id="4632d-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="4632d-312">Yukarıdaki örneğe dönerek, `Map` bir tane olmak üzere bir tane olmak üzere tür parametrelerine ihtiyacım olduğunu `fn` ve çıktının temsil edilebilmesi için bir tane olduğunu görebiliriz `fn` .</span><span class="sxs-lookup"><span data-stu-id="4632d-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="4632d-313">Q # dilinde, bu, `<>` {} bildiriminde bir işlev veya işlemin adından sonra ve her tür parametresini listeleyerek açılı ayraçlar (brakets $ \braket $! değil) eklenerek yazılır.</span><span class="sxs-lookup"><span data-stu-id="4632d-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="4632d-314">Her tür parametresinin adı bir Tick ile başlamalı `'` ve sıradan bir tür ( *somut* tür olarak da bilinir) değil bir tür parametresi olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="4632d-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="4632d-315">İçin bu `Map` nedenle şunu yazıyoruz:</span><span class="sxs-lookup"><span data-stu-id="4632d-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="4632d-316">Tanımının, daha `Map<'Input, 'Output>` önce yazdığımız sürümlere çok benzer şekilde göründüğünü unutmayın.</span><span class="sxs-lookup"><span data-stu-id="4632d-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="4632d-317">Tek fark, derleyiciye doğrudan bağlı olmayan ve ne olduğunu açıkça belirttiğimiz `Map` `'Input` `'Output` , ancak bunları dolaylı olarak aracılığıyla kullanarak her iki tür için de bir bütün olarak bildirdik `fn` .</span><span class="sxs-lookup"><span data-stu-id="4632d-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="4632d-318">Bu şekilde tanımlandıktan sonra `Map<'Input, 'Output>` , bunu sıradan bir işlev gibi çağırabiliriz:</span><span class="sxs-lookup"><span data-stu-id="4632d-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="4632d-319">Genel işlevler ve işlemler yazmak, "kayıt düzeni-Out" ın Q # işlevleri ve işlemlerini düşünmek için çok faydalı bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="4632d-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="4632d-320">Her işlev tam olarak bir giriş yaptığından ve tam olarak bir çıkış döndürdüğünden, türünde bir giriş `'T -> 'U` *herhangi* bir Q # işleviyle eşleşir.</span><span class="sxs-lookup"><span data-stu-id="4632d-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="4632d-321">Benzer şekilde, herhangi bir işlem türünde bir girişe geçirilebilir `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="4632d-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="4632d-322">İkinci bir örnek olarak, iki diğer işlevin birleşimini döndüren bir işlev yazma sınamasını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="4632d-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="4632d-323">Burada, tam olarak ne, ve ne olduğunu belirtmemiz gerekir `A` `B` `C` . bu nedenle, yeni işlevimizin yardımcı programını ciddi ölçüde kısıtlar `Compose` .</span><span class="sxs-lookup"><span data-stu-id="4632d-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="4632d-324">All,,, ve ile `Compose` bağlıdır `A` `B` `C` *via* `innerFn` `outerFn` .</span><span class="sxs-lookup"><span data-stu-id="4632d-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="4632d-325">Alternatif olarak,,, `Compose` ve için çalıştığını belirten tür parametreleri ekleyebiliriz *any* `A` `B` `C` ve bu parametrelerin, ve ile beklenen olanlarla eşleştiği sürece `innerFn` `outerFn` :</span><span class="sxs-lookup"><span data-stu-id="4632d-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="4632d-326">Q # standart kitaplıkları, daha yüksek sıralı denetim akışı hızlı bir şekilde daha kolay hale getirmek için tür parametreli işlem ve işlev aralığı sağlar.</span><span class="sxs-lookup"><span data-stu-id="4632d-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="4632d-327">Bunlar, [Q # standart kitaplığı kılavuzunda](xref:microsoft.quantum.libraries.standard.intro)daha ayrıntılı olarak ele alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="4632d-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="4632d-328">Ilk sınıf değerleri olarak callables</span><span class="sxs-lookup"><span data-stu-id="4632d-328">Callables as First-Class Values</span></span>

<span data-ttu-id="4632d-329">İşlemler yerine işlevleri kullanarak denetim akışı ve klasik mantık hakkında önemli bir tekniktir, bu işlemler ve Q # içindeki işlevler *birinci sınıf*olur.</span><span class="sxs-lookup"><span data-stu-id="4632d-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="4632d-330">Diğer bir deyişle, her bir değer kendi sağ tarafındaki dilde değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="4632d-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="4632d-331">Örneğin, daha az dolaylı bir değer varsa, aşağıdakiler mükemmel bir Q # kodudur:</span><span class="sxs-lookup"><span data-stu-id="4632d-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="4632d-332">`ourH`Yukarıdaki kod parçacığında değişkenin değeri, daha sonra <xref:microsoft.quantum.intrinsic.h> Bu değeri başka bir işlem gibi çağırabilmemiz için işlem olur.</span><span class="sxs-lookup"><span data-stu-id="4632d-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="4632d-333">Bu, daha yüksek sıralı denetim akışı kavramlarını oluşturan, işlemleri girişin bir parçası olarak alan işlemleri yazmamızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="4632d-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="4632d-334">Örneğin, aynı hedef qubit 'e iki kez uygulanarak bir işlemi "kare" olarak ele geçirebilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="4632d-335">İşlevden işlem döndürme</span><span class="sxs-lookup"><span data-stu-id="4632d-335">Returning operations from a function</span></span>

<span data-ttu-id="4632d-336">İşlemler, bir işlem biçiminde bir hisse programın açıklamasını döndüren klasik bir işlev olarak bazı klasik koşullu mantığı ayırabilmemiz gibi, işlemleri çıktıların bir parçası olarak de döndürebiliyoruz.</span><span class="sxs-lookup"><span data-stu-id="4632d-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="4632d-337">Basit bir örnek olarak, iki bitlik bir klasik ileti alan tarafın, bu iletiyi kullanarak doğru bir teleporm durumuna ulaşmasını sağlamak için ileti kullanması gereken teleporsyon örneğini düşünün.</span><span class="sxs-lookup"><span data-stu-id="4632d-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="4632d-338">Bunu, bu iki klasik biti alan ve uygun kod çözme işlemini döndüren bir işlev açısından yazalım.</span><span class="sxs-lookup"><span data-stu-id="4632d-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="4632d-339">Bu yeni işlev aslında bir işlevdir, ancak aynı ve değerlerini aynı şekilde çağırırsanız `hereBit` `thereBit` , her zaman aynı işlemi geri alacaksınız.</span><span class="sxs-lookup"><span data-stu-id="4632d-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="4632d-340">Bu nedenle, kod çözme mantığının farklı işlem özelleştirmelerinin tanımlarıyla nasıl etkileşime gireceğini öğrenmek zorunda kalmadan güvenli şekilde işlemler içinde çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="4632d-341">Diğer bir deyişle, bir işlev içinde klasik mantığı yalıtdık ve bu, bir derleyicinin işlev çağrısının Impunity ile yeniden düzenlenmesine ve girişin korunduğu sürece bir şekilde yeniden sıralanacağını kabul ettik.</span><span class="sxs-lookup"><span data-stu-id="4632d-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="4632d-342">Kısmi uygulama</span><span class="sxs-lookup"><span data-stu-id="4632d-342">Partial Application</span></span>

<span data-ttu-id="4632d-343">*Kısmi uygulama*kullanarak işlem döndüren işlevlerle çok daha fazlasını yapabiliriz, burada, girişin bir veya daha fazla bölümünü bir işleve veya işleme bir veya daha fazla şekilde aramadan sağlayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="4632d-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="4632d-344">Örneğin, yukarıdaki örneği geri çektireceğiz, `ApplyTwice` giriş işleminin hangi qubit 'e uygulanacağını, doğru bir şekilde belirtmek istediğimiz olduğunu belirtebiliriz:</span><span class="sxs-lookup"><span data-stu-id="4632d-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="4632d-345">Bu durumda, yerel değişken `twiceOp` kısmen uygulanan işlemi tutar `ApplyTwice(op, _)` ; burada, girişin henüz belirtilmemiş olduğu parçalar tarafından gösterilir `_` .</span><span class="sxs-lookup"><span data-stu-id="4632d-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="4632d-346">Aslında bir sonraki satırda arama yaptığımız zaman `twiceOp` , girişin kalan tüm bölümlerinin özgün işleme göre kısmen uygulanmış işleme giriş olarak geçeceğiz.</span><span class="sxs-lookup"><span data-stu-id="4632d-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="4632d-347">Bu nedenle, yukarıdaki kod parçacığı, `ApplyTwice(op, target)` doğrudan çağrılmasıyla daha da benzer bir şekilde, girişin bazı parçalarını sağlarken çağrıyı gecikmemizi sağlayan yeni bir yerel değişken sunuyoruz.</span><span class="sxs-lookup"><span data-stu-id="4632d-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="4632d-348">Kısmen uygulanmış bir işlem, tüm giriş sağlanana kadar gerçekten çağrılmadığı için, işlevleri içinden bile işlemleri güvenle uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="4632d-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="4632d-349">Prensibi, içindeki klasik mantık çok `SquareOperation` daha fazla olabilir, ancak derleyicinin işlevler hakkında sunabileceği garantilere göre bir işlemin geri kalanından yalıtılmıştır.</span><span class="sxs-lookup"><span data-stu-id="4632d-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="4632d-350">Bu yaklaşım, klasik denetim akışını hisse uygun şekilde kullanılmak üzere bir şekilde ifade etmek için Q # standart kitaplığı genelinde kullanılacaktır.</span><span class="sxs-lookup"><span data-stu-id="4632d-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="4632d-351">Özyineleme</span><span class="sxs-lookup"><span data-stu-id="4632d-351">Recursion</span></span>

<span data-ttu-id="4632d-352">Q # callables 'in doğrudan veya dolaylı olarak özyinelemeli olmasına izin verilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="4632d-353">Diğer bir deyişle, bir işlem veya işlev kendisini çağırabilir veya çağrılabilir işlemi doğrudan veya dolaylı olarak çağıran başka bir çağrılabilir çağrısı sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="4632d-354">Ancak özyineleme kullanımı hakkında iki önemli yorum vardır:</span><span class="sxs-lookup"><span data-stu-id="4632d-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="4632d-355">İşlemlerde özyineleme kullanımı, bazı iyileştirmelere engel olabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="4632d-356">Bu, algoritmanın yürütme süresi üzerinde önemli bir etkiye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="4632d-357">Gerçek bir hisse cihazında yürütme yaparken, yığın alanı sınırlı olabilir ve bu nedenle derin özyineleme bir çalışma zamanı hatasına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="4632d-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="4632d-358">Özellikle, Q # derleyicisi ve çalışma zamanı, kuyruk özyinelemeyi tanımlamaz ve iyileştirmez.</span><span class="sxs-lookup"><span data-stu-id="4632d-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4632d-359">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="4632d-359">Next steps</span></span>

<span data-ttu-id="4632d-360">Q # [değişkenleri](xref:microsoft.quantum.guide.variables) hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="4632d-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>