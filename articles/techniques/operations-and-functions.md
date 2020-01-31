---
title: 'İşlemler ve işlevler-Q # teknikleri | Microsoft Docs'
description: 'İşlemler ve işlevler-Q # teknikleri'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fca20bb44cc42008f7d25d2fc71a39b962525c2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820785"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="3a671-103">S # Işlem ve Işlevleri</span><span class="sxs-lookup"><span data-stu-id="3a671-103">Q# Operations and Functions</span></span>

<span data-ttu-id="3a671-104">S # programları, bir veya daha fazla *işlemden* oluşur. Bu işlem, bir veya daha fazla işlem ve klasik verilerde değişikliklere izin veren bir veya daha fazla *işlev* olabilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="3a671-105">İşlemlere karşılık işlevler, tamamen klasik davranışı betimleyen ve klasik çıkış değerlerini hesaplama konusunda herhangi bir etkiye sahip olmayan işlevler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3a671-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="3a671-106">Q # içinde tanımlanan her işlem, dil tarafından tanımlanan yerleşik iç işlemler de dahil olmak üzere herhangi bir sayıda işlemi çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="3a671-107">Bu iç işlemlerin tanımlandığı belirli yol, hedef makineye bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="3a671-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="3a671-108">Derlendiğinde, her işlem hedef makinelere sağlanlenebilecek bir .NET sınıf türü olarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="3a671-109">Yeni Işlemleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="3a671-109">Defining New Operations</span></span>

<span data-ttu-id="3a671-110">Yukarıda açıklandığı gibi, Q # dilinde yazılmış bir hisse programının en temel yapı taşı, klasik .NET uygulamalarından çağrılabilen bir *işlemdir*. Örneğin, simülatör veya Q # içindeki diğer işlemler tarafından çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="3a671-111">Her işlem bir girdi alır, bir çıktı üretir ve bir veya daha fazla işlem uzmanlığını için uygulamayı belirtir.</span><span class="sxs-lookup"><span data-stu-id="3a671-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="3a671-112">Örneğin, aşağıdaki işlem yalnızca bir varsayılan gövde özelleştirmesi tanımlar ve giriş olarak tek bir qubit alır, ardından bu girişte yerleşik `X` işlemini çağırır:</span><span class="sxs-lookup"><span data-stu-id="3a671-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="3a671-113">Anahtar sözcüğü `operation` işlem tanımını başlatır ve ardından adı gelir; Burada `BitFlip`.</span><span class="sxs-lookup"><span data-stu-id="3a671-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="3a671-114">Sonra, girişin türü, yeni işlemdeki girişe başvurmak için bir ad `target` birlikte `Qubit`olarak tanımlanır.</span><span class="sxs-lookup"><span data-stu-id="3a671-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="3a671-115">Benzer şekilde, `Unit` işlemin çıktısının boş olduğunu tanımlar.</span><span class="sxs-lookup"><span data-stu-id="3a671-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="3a671-116">Bu, ve diğer zorunlu dillerde `void` C# benzer ve içindeki F# `unit` ve diğer işlevsel dillerde eşdeğerdir.</span><span class="sxs-lookup"><span data-stu-id="3a671-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="3a671-117">Bu konuda daha ayrıntılı bilgiler bulabilirsiniz, ancak her Q # işlemi tam olarak bir giriş alır ve tam olarak bir çıktı döndürür.</span><span class="sxs-lookup"><span data-stu-id="3a671-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="3a671-118">Birden çok giriş ve çıkış daha sonra birden çok değeri tek bir değerde toplamak için *Tanımlama grupları*kullanılarak temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="3a671-119">Bu durumda, Q # ' ın bir "demet oluşturma" dili olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="3a671-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="3a671-120">Bu kavramı izleyerek, `()` `Unit`tür olan "boş" kayıt düzeni olarak okunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3a671-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="3a671-121">Yeni işlem içinde, yalnızca varsayılan gövde özelleştirmesi uygulamasının açıkça belirtilmesi gerekiyorsa, uygulama doğrudan bildirim içinde belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="3a671-122">Ayrıca, örneğin, bir veya daha fazla `functor` işlemi için aşağıda ayrıntılı gibi uygulamaları tanımlamak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="3a671-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="3a671-123">Yukarıdaki örnekte, tek bildiri yerleşik Q # işlemini <xref:microsoft.quantum.intrinsic.x>çağırmadır.</span><span class="sxs-lookup"><span data-stu-id="3a671-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="3a671-124">İşlemler ayrıca `Unit`daha ilginç türler döndürebilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="3a671-125">Örneğin, <xref:microsoft.quantum.intrinsic.m> işlemi, ölçüm gerçekleştirmemiş olduğunu temsil eden `Result`türünde bir çıktı döndürür.</span><span class="sxs-lookup"><span data-stu-id="3a671-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="3a671-126">Bir işlemden çıkışı başka bir işleme geçirebiliriz ya da yeni bir değişken tanımlamak için `let` anahtar sözcüğüyle kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3a671-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="3a671-127">Bu, yoğun kodlama gibi düşük bir düzeyde hisse uygun olan klasik hesaplamayı temsil etmenizi sağlar:</span><span class="sxs-lookup"><span data-stu-id="3a671-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="3a671-128">Funörler, adjoint ve kontrollü</span><span class="sxs-lookup"><span data-stu-id="3a671-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="3a671-129">Bir işlem Unitary dönüştürmesi uygularsa, *adjointed* veya *denetimli*olduğunda işlemin nasıl davrandığını tanımlamak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="3a671-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="3a671-130">Bir işlemin adeksiz özelleştirmesi, geriye doğru çalıştırıldığında bir işlemin nasıl davrandığının, denetimli bir özelleşmenin, bir hisse kayıt durumuna göre uygulanması durumunda işlemin nasıl davrandığının belirtir.</span><span class="sxs-lookup"><span data-stu-id="3a671-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="3a671-131">Bu uzmanlıklar, işlem imzasının bir parçası olarak bildirilebilecek: aşağıdaki örnekte `is Adj + Ctl`.</span><span class="sxs-lookup"><span data-stu-id="3a671-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="3a671-132">Bu tür örtülü olarak tanımlanmış her özelleştirme için karşılık gelen uygulama derleyici tarafından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="3a671-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="3a671-133">Q # ' daki birçok işlem Unitary kapılarını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3a671-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="3a671-134">$U $, bir işlem `U`temsil eden Unitary kapısıdır `Adjoint U`, "^ \dağılım $ $U Unitary geçidini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3a671-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="3a671-135">Uygulamanın derleyici tarafından üretilebileceği durumda, açıkça belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="3a671-136">Bu tür açık özelleşmeler, uygun bir oluşturma yönergesinin veya Kullanıcı tanımlı bir uygulamadan oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="3a671-137">Örneğin, yukarıdaki `PrepareEntangledPair` kod, açık özelleştirme bildirimlerini içeren aşağıdaki koda eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="3a671-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
<span data-ttu-id="3a671-138">Anahtar sözcüğü `auto`, derleyicinin özelleşme uygulamasının nasıl oluşturulacağını belirlemesi gerektiğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="3a671-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="3a671-139">Derleyici belirli bir özelleşmenin uygulamasını otomatik olarak üretemiyor veya daha verimli bir uygulama verilirse, uygulama da el ile tanımlanabilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="3a671-140">Yukarıdaki örnekte, `adjoint invert;`, adjoint özelleşmesinin gövde uygulamasını tersine getirerek oluşturulacağını ve `controlled adjoint invert;` denetlenen majoint özelleşmesinin, denetlenen özelleşmenin belirtilen uygulamasını tersine ayırarak oluşturulacağını belirtir.</span><span class="sxs-lookup"><span data-stu-id="3a671-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="3a671-141">Daha [yüksek sıralı Denetim akışında](xref:microsoft.quantum.concepts.control-flow)buna daha fazla örnek görüyoruz.</span><span class="sxs-lookup"><span data-stu-id="3a671-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="3a671-142">Bir işlemin özelleşmesi çağırmak için `Adjoint` veya `Controlled` anahtar sözcüklerini kullanın.</span><span class="sxs-lookup"><span data-stu-id="3a671-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="3a671-143">Örneğin, yukarıdaki üst bilgi kodlama örneği, entangled durumunun bir qubit çiftiyle geri dönüştürülmesi için `PrepareEntangledPair` adjoint kullanılarak daha fazla sıkı yazılabilir:</span><span class="sxs-lookup"><span data-stu-id="3a671-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="3a671-144">Funlar ile kullanım için işlemleri tasarlarken göz önünde bulundurmanız gereken bazı önemli sınırlamalar vardır.</span><span class="sxs-lookup"><span data-stu-id="3a671-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="3a671-145">Aynı etkiyi elde etmek için bu tür bir işlemde deyimleri yeniden sıralamak belirsiz olduğundan, başka bir işlemin çıkış değerini kullanan bir işlem için en kritik öneme sahip olan uzmanlık, derleyici tarafından otomatik olarak üretilemez.</span><span class="sxs-lookup"><span data-stu-id="3a671-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="3a671-146">Yeni Işlevleri tanımlama</span><span class="sxs-lookup"><span data-stu-id="3a671-146">Defining New Functions</span></span>

<span data-ttu-id="3a671-147">Q #, bir çıkış değeri hesaplamasının ötesinde etkileri olmasına izin verilmediği için işlemlerden farklı olan *işlevleri*tanımlamaya de olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="3a671-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="3a671-148">Özellikle, işlevler işlemleri çağıramaz, qubits üzerinde işlem, örnek rastgele sayılar veya başka türlü giriş değerinin ötesinde bir işleve bağımlı duruma bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="3a671-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="3a671-149">Sonuç olarak, Q # işlevleri *saf*olduğundan, her zaman aynı giriş değerlerini aynı çıkış değerleriyle eşleştirirler.</span><span class="sxs-lookup"><span data-stu-id="3a671-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="3a671-150">Bu, Q # derleyicisinin, işlem uzmanlıklarını oluştururken işlevleri nasıl ve ne zaman çağırdığını güvenle yeniden sıralamak için izin verir.</span><span class="sxs-lookup"><span data-stu-id="3a671-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="3a671-151">Bir işlev tanımlamak, bir işlev için hiçbir adjoint veya denetimli uzmanlık tanımlanmamasının dışında, bir işlemi tanımlamaya benzer şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="3a671-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="3a671-152">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="3a671-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="3a671-153">Bunu yapmak mümkün olduğunda, işlemler içinden daha kolay bir şekilde kullanılabilmesi için klasik mantığı işlemler yerine işlevler bakımından yazmak yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="3a671-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="3a671-154">Örneğin, bir işlem olarak `Square` yazdık, derleyici aynı girişe çağrı yapan aynı çıktıyı tutarlı bir şekilde ürettireceğiz.</span><span class="sxs-lookup"><span data-stu-id="3a671-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="3a671-155">İşlevler ve işlemler arasındaki farkın altını bir şekilde çözmek için, bir Q # işlemi içinden rastgele bir sayı örnekleme sorununu ele alalım:</span><span class="sxs-lookup"><span data-stu-id="3a671-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="3a671-156">`U` her çağrıldığında, `target`farklı bir eyleme sahip olur.</span><span class="sxs-lookup"><span data-stu-id="3a671-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="3a671-157">Derleyici, `U`için `adjoint auto` bir özelleştirme bildirimi eklediğimiz takdirde, `U(target); Adjoint U(target);` kimlik (yani, No-Op) olarak hareket eder.</span><span class="sxs-lookup"><span data-stu-id="3a671-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="3a671-158">Bu, [vektörlerin ve matrislerde](xref:microsoft.quantum.concepts.vectors)gördüğdiğimiz adjoint 'in tanımını ihlal ediyor. bu şekilde, işlemi çağırdığımız bir işlemde bir adjoint özelleşmesinin otomatik olarak oluşturmaya izin veren <xref:microsoft.quantum.math.randomreal>, derleyici tarafından verilen garantileri bozuyor; <xref:microsoft.quantum.math.randomreal>, hiçbir adjoint veya kontrollü sürüm bulunmayan bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="3a671-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="3a671-159">Öte yandan, `Square` gibi işlev çağrılarına izin vermek, derleyicinin çıktının kararlı kalmasını sağlamak için yalnızca `Square` girişi korumasının gerektiği konusunda emin olabilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="3a671-160">Bu nedenle, işlevlerde mümkün olduğunca klasik mantığı yalıtmak, diğer işlevlerde ve işlemlerde bu mantığı yeniden kullanmayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="3a671-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="3a671-161">Denetim Akışı</span><span class="sxs-lookup"><span data-stu-id="3a671-161">Control Flow</span></span>

<span data-ttu-id="3a671-162">Bir işlem veya işlev içinde her bir ifade, en sık kullanılan zorunlu klasik dillere benzer şekilde sırayla yürütülür.</span><span class="sxs-lookup"><span data-stu-id="3a671-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="3a671-163">Bu denetim akışı, ancak üç farklı şekilde değiştirilebilir:</span><span class="sxs-lookup"><span data-stu-id="3a671-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="3a671-164">`if` deyimleri</span><span class="sxs-lookup"><span data-stu-id="3a671-164">`if` Statements</span></span>
- <span data-ttu-id="3a671-165">`for` döngüleri</span><span class="sxs-lookup"><span data-stu-id="3a671-165">`for` Loops</span></span>
- <span data-ttu-id="3a671-166">`repeat`-`until` döngüleri</span><span class="sxs-lookup"><span data-stu-id="3a671-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="3a671-167">[Başarılı olana kadar yineleme (ru)](xref:microsoft.quantum.techniques.qubits#measurements) devrelerine kadar, son tartışmayı erteliyoruz.</span><span class="sxs-lookup"><span data-stu-id="3a671-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="3a671-168">Ancak `if` ve `for` denetim akışı yapıları, klasik programlama dillerinin çoğu için tanıdık bir anlata devam ediyor.</span><span class="sxs-lookup"><span data-stu-id="3a671-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="3a671-169">Özellikle, bir `if` deyimi bir koşul alabilir, bir veya daha fazla `elif` deyimi gelebilir ve bir `else`ile bitemez:</span><span class="sxs-lookup"><span data-stu-id="3a671-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="3a671-170">Benzer şekilde, `for` döngüleri bir dizi tamsayı veya bir dizinin öğeleri üzerinde yinelemeyi gösterir:</span><span class="sxs-lookup"><span data-stu-id="3a671-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="3a671-171">Önemlisi, `for` döngüleri ve `if` deyimleri, özelleştirilmiş oluşturmaları otomatik olarak oluşturulan işlemlerde bile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="3a671-172">Bu durumda `for` döngüsünün adeki yönü tersine çevirir ve her yinelemenin adeklerini alır.</span><span class="sxs-lookup"><span data-stu-id="3a671-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="3a671-173">Bu, "ayakkabılar-ve-SOCKS" ilkesini izler: Socks ' yi almayı geri almak istiyorsanız, ve ardından</span><span class="sxs-lookup"><span data-stu-id="3a671-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="3a671-174">Bu işlem, siz de daha az bir işlem yapmaya çalışır.</span><span class="sxs-lookup"><span data-stu-id="3a671-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="3a671-175">Ilk sınıf değerleri olarak işlemler ve Işlevler</span><span class="sxs-lookup"><span data-stu-id="3a671-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="3a671-176">İşlemler yerine işlevleri kullanarak denetim akışı ve klasik mantık hakkında önemli bir tekniktir, bu işlemler ve Q # içindeki işlevler *birinci sınıf*olur.</span><span class="sxs-lookup"><span data-stu-id="3a671-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="3a671-177">Diğer bir deyişle, her bir değer kendi sağ tarafındaki dilde değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="3a671-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="3a671-178">Örneğin, daha az dolaylı bir değer varsa, aşağıdakiler mükemmel bir Q # kodudur:</span><span class="sxs-lookup"><span data-stu-id="3a671-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="3a671-179">Yukarıdaki kod parçacığında `ourH` değişkenin değeri, işlem <xref:microsoft.quantum.intrinsic.h>ve bu değeri diğer tüm işlemler gibi çağırabiliriz.</span><span class="sxs-lookup"><span data-stu-id="3a671-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="3a671-180">Bu, daha yüksek sıralı denetim akışı kavramlarını oluşturan, işlemleri girişin bir parçası olarak alan işlemleri yazmamızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="3a671-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="3a671-181">Örneğin, aynı hedef qubit 'e iki kez uygulanarak bir işlemi "kare" olarak ele geçirebilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="3a671-182">Bu örnekte, tür `(Qubit => Unit)` görüntülenen `=>` ok, giriş `op` alanının, türü `Qubit` giriş olarak alan ve çıktısı olarak boş bir tanımlama grubu üreten bir işlem olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="3a671-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="3a671-183">Ayrıca, bu işlem türünün özelliklerini belirttik ve bu, hangi funın desteklendiği hakkındaki bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="3a671-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="3a671-184">`(Qubit => Unit)` bir işlem `Adjoint` veya `Controlled` functor desteklemiyor.</span><span class="sxs-lookup"><span data-stu-id="3a671-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="3a671-185">Bu tür bir işlemin, örneğin `Adjoint` functor desteğine sahip olduğunu belirtmek istiyoruz, bunu adjointable olarak bildirmemiz gerekir.</span><span class="sxs-lookup"><span data-stu-id="3a671-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="3a671-186">Bu, türü `is Adj` ek açıklama kullanılarak yapılır.</span><span class="sxs-lookup"><span data-stu-id="3a671-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="3a671-187">Benzer şekilde, `(Qubit => Unit is Ctl)` bu tür bir işlemin `Controlled` functor 'ı desteklediğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="3a671-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="3a671-188">Bu konuda [Q # ' daki türler (XREF: Microsoft. hisse. Language. Type-model) daha genel olarak tartışıyoruz.</span><span class="sxs-lookup"><span data-stu-id="3a671-188">We will explore this further when we discuss [types in Q#] (xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="3a671-189">Şimdilik, işlem biçiminde bir hisse programının açıklamasını döndüren klasik bir işlev olarak bazı klasik koşullu mantığı ayırabilmemiz gibi, işlemleri çıkışların bir parçası olarak de döndürebiliriz.</span><span class="sxs-lookup"><span data-stu-id="3a671-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="3a671-190">Basit bir örnek olarak, iki bitlik bir klasik ileti alan tarafın, bu iletiyi kullanarak doğru bir teleporm durumuna ulaşmasını sağlamak için ileti kullanması gereken teleporsyon örneğini düşünün.</span><span class="sxs-lookup"><span data-stu-id="3a671-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="3a671-191">Bunu, bu iki klasik biti alan ve uygun kod çözme işlemini döndüren bir işlev açısından yazalım.</span><span class="sxs-lookup"><span data-stu-id="3a671-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="3a671-192">Bu yeni işlev, `hereBit` ve `thereBit`aynı değerlerle çağırırsanız, her zaman aynı işlemi geri alacak.</span><span class="sxs-lookup"><span data-stu-id="3a671-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="3a671-193">Bu nedenle, kod çözme mantığının farklı işlem özelleştirmelerinin tanımlarıyla nasıl etkileşime gireceğini öğrenmek zorunda kalmadan güvenli şekilde işlemler içinde çalıştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="3a671-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="3a671-194">Diğer bir deyişle, bir işlev içinde klasik mantığı yalıtdık ve bu, bir derleyicinin işlev çağrısının Impunity ile yeniden düzenlenmesine ve girişin korunduğu sürece bir şekilde yeniden sıralanacağını kabul ettik.</span><span class="sxs-lookup"><span data-stu-id="3a671-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="3a671-195">Ayrıca, [işlemler ve işlev türlerini](#operations-and-functions-as-first-class-values)tartıştığımız zaman daha ayrıntılı olarak göreceğiniz için işlevleri birinci sınıf değerler olarak kabul eteceğiz.</span><span class="sxs-lookup"><span data-stu-id="3a671-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="3a671-196">Işlemler ve Işlevler kısmen uygulanıyor</span><span class="sxs-lookup"><span data-stu-id="3a671-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="3a671-197">*Kısmi uygulama*kullanarak işlem döndüren işlevlerle çok daha fazlasını yapabiliriz, burada, girişin bir veya daha fazla bölümünü bir işleve veya işleme bir veya daha fazla şekilde aramadan sağlayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="3a671-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="3a671-198">Örneğin, yukarıdaki `ApplyTwice` örneğini geri çektireceğiz, giriş işleminin hangi qubit 'e uygulanacağını, doğru bir şekilde belirtmek istediğimiz belirtebiliriz:</span><span class="sxs-lookup"><span data-stu-id="3a671-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="3a671-199">Bu durumda `twiceOp` yerel değişkeni, henüz belirtilmemiş olan girişlerin `_`tarafından belirtildiği, kısmen uygulanan işlem `ApplyTwice(op, _)`barındırır.</span><span class="sxs-lookup"><span data-stu-id="3a671-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="3a671-200">Aslında bir sonraki satırda `twiceOp` çağırdığımızda, girişin geri kalan bölümlerinin tümü için kısmen uygulanmış işleme giriş olarak geçeceğiz.</span><span class="sxs-lookup"><span data-stu-id="3a671-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="3a671-201">Bu nedenle, yukarıdaki kod parçacığı, `ApplyTwice(op, target)` doğrudan çağrılmasıyla daha da benzer bir şekilde, girişin bazı parçalarını sağlarken çağrıyı gecikmemizi sağlayan yeni bir yerel değişken sunuyoruz.</span><span class="sxs-lookup"><span data-stu-id="3a671-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="3a671-202">Kısmen uygulanmış bir işlem, tüm giriş sağlanana kadar gerçekten çağrılmadığı için, işlevleri içinden bile işlemleri güvenle uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3a671-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="3a671-203">Prensibi, `SquareOperation` içindeki klasik mantık çok daha fazla olabilir, ancak derleyicinin işlevleri hakkında sunabileceği garantilere göre, hala işlemin geri kalanından yalıtılmıştır.</span><span class="sxs-lookup"><span data-stu-id="3a671-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="3a671-204">Bu yaklaşım, klasik denetim akışını hisse uygun şekilde kullanılmak üzere bir şekilde ifade etmek için Q # standart kitaplığı genelinde kullanılacaktır.</span><span class="sxs-lookup"><span data-stu-id="3a671-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
