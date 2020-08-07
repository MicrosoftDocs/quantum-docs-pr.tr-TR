---
title: Q#Temel bilgileri
description: Temel kavramlarıQ#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4f4a75cdaaa070fd763d7f75429b7c39357d25a5
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869656"
---
# <a name="no-locq-basics"></a><span data-ttu-id="d3ef3-103">Q#Temel bilgileri</span><span class="sxs-lookup"><span data-stu-id="d3ef3-103">Q# Basics</span></span>

<span data-ttu-id="d3ef3-104">Bu makalede, uygulamasının temel yapı taşları hakkında kısa bir giriş sunulmaktadır Q# .</span><span class="sxs-lookup"><span data-stu-id="d3ef3-104">This article presents a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="d3ef3-105">Ne olduğuna ve ne tür bir genel bakış, Q# hisse geliştirme setinin temel bir bileşeni olarak sığıyorsa, bkz. [nedir Q# ?](xref:microsoft.quantum.overview.q-sharp).</span><span class="sxs-lookup"><span data-stu-id="d3ef3-105">For an overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, see [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="d3ef3-106">Hisse bir program nedir?</span><span class="sxs-lookup"><span data-stu-id="d3ef3-106">What is a quantum program?</span></span>

<span data-ttu-id="d3ef3-107">Teknik açıdan, hisse, çağrıldığında, belirli işlemleri bir hisse sisteminde gerçekleştirirken belirli bir klasik alt yordam kümesidir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-107">From a technical perspective, a quantum program is a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="d3ef3-108">Bu görünümün önemli bir sonucu Q# , bir programın yalnızca qubits 'i doğrudan modelleyemediğini, ancak bunun yerine, belirli bir şekilde denetlenen bilgisayarın bu qubits ile nasıl etkileşime gireceğini açıklar.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-108">An important consequence of that view is that a Q# program does not directly model qubits themselves, but rather describes how a classically controlled computer interacts with those qubits.</span></span>
<span data-ttu-id="d3ef3-109">Tasarıma göre, Q# doğrudan hisse tlar veya diğer hisse kutları özelliklerini tanımlamaz.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-109">By design, Q# does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="d3ef3-110">Örneğin, hisse bilgi Işlem kavramları kılavuzunda $ \ket{+} = \left (\ket {0} + \ket {1} \ right)/\sqrt $ durumunu göz önünde bulundurun {2} . [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="d3ef3-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="d3ef3-111">Bu durumu içinde hazırlamak için Q# , qubits 'in $ \ket $ durumunda başlatıldığı olgularla başlayın {0} ve bu $ \ket{+} = H\ket {0} $, burada $H $, [ `H` Işlem](xref:microsoft.quantum.intrinsic.h)tarafından uygulanan [Hadamard Transform](xref:microsoft.quantum.glossary#hadamard)şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-111">To prepare this state in Q#, start with the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the [Hadamard transform](xref:microsoft.quantum.glossary#hadamard), implemented by the [`H` operation](xref:microsoft.quantum.intrinsic.h).</span></span> <span data-ttu-id="d3ef3-112">Q#Bir qubit başlatmak ve dönüştürmek için temel kod, ardından şöyle görünür:</span><span class="sxs-lookup"><span data-stu-id="d3ef3-112">The basic Q# code to initialize and transform a qubit, then, looks like this:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
<span data-ttu-id="d3ef3-113">Başlatma veya *ayırma*hakkında daha fazla bilgi için bkz. [qubits ile çalışma](xref:microsoft.quantum.guide.qubits).</span><span class="sxs-lookup"><span data-stu-id="d3ef3-113">For more information on initializing, or *allocating*, qubits, see [Working with qubits](xref:microsoft.quantum.guide.qubits).</span></span>

## <a name="quantum-states-in-no-locq"></a><span data-ttu-id="d3ef3-114">Hisse ve ABDQ#</span><span class="sxs-lookup"><span data-stu-id="d3ef3-114">Quantum states in Q#</span></span>

<span data-ttu-id="d3ef3-115">Daha önemlisi, önceki program içindeki duruma açıkça başvurmaz Q# ancak programımızın durumu nasıl *dönüştürdüğünü* açıklamaz.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-115">Importantly, the previous program does not explicitly refer to the state within Q# but described how our program *transformed* the state.</span></span>
<span data-ttu-id="d3ef3-116">Bu yaklaşımda, her bir hedef makinede bile, makineye bağlı farklı yorumlamalar olabilecek, her bir bir hisse amadığına ilişkin olarak ne *kadar büyük bir işlem olduğu* hakkında tamamen belirsiz bir durum söz konusu olabilir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-116">With this approach, you can be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="d3ef3-117">Bir Q# Program, qubit 'in durumuna introspect.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-117">A Q# program cannot introspect into the state of a qubit.</span></span>
<span data-ttu-id="d3ef3-118">Bunun yerine, bir program [`Measure`](xref:microsoft.quantum.intrinsic.measure) qubit 'ten bilgi almak için gibi işlemleri çağırabilir ve [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) bir qubit durumu üzerinde işlem yapmak için ve gibi işlemleri çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-118">Instead, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="d3ef3-119">Bu *işlemler aslında yalnızca* belirli bir programı çalıştırmak için kullanılan hedef makine tarafından somut hale getirilir Q# .</span><span class="sxs-lookup"><span data-stu-id="d3ef3-119">What these operations actually *do* is only made concrete by the target machine used to run the particular Q# program.</span></span>
<span data-ttu-id="d3ef3-120">Örneğin, programı [tam durum benzeticimizde](xref:microsoft.quantum.machines.full-state-simulator)çalıştırırsanız simülatör, sanal hisse sisteme karşılık gelen matematiksel işlemleri gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-120">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="d3ef3-121">Ancak geleceğe bağlı olarak, hedef makine gerçek bir hisse bilgisayar olduğunda, bu tür işlemleri çağırmak, Q# hisse bilgisayarını *Gerçek* hisse sisteminde ilgili *Gerçek* işlemleri gerçekleştirmeye yönlendirir, örneğin, tam olarak zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-121">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# directs the quantum computer to perform the corresponding *real* operations on the *real* quantum system, for example, precisely timed laser pulses).</span></span>

<span data-ttu-id="d3ef3-122">Q#Program, bu işlemleri bir hedef makine tarafından tanımlandığı şekilde yeniden birleştirir. Express, hızlı bir şekilde yeni ve yüksek düzey işlemler oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-122">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="d3ef3-123">Bu şekilde, Q# temel alınan hisse ve hibrit-klasik algoritmaların yanı sıra bir hedef makine ya da simülatör yapısına göre genel de olan mantıksal ve karma hisse</span><span class="sxs-lookup"><span data-stu-id="d3ef3-123">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="no-locq-operations-and-functions"></a><span data-ttu-id="d3ef3-124">Q#işlemler ve işlevler</span><span class="sxs-lookup"><span data-stu-id="d3ef3-124">Q# operations and functions</span></span>

<span data-ttu-id="d3ef3-125">Bir Q# Program, *işlemler*, *işlevler*ve Kullanıcı tanımlı türler içerir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-125">Concretely, a Q# program comprises *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="d3ef3-126">İşlemler, hisse sistemleri ve en temel yapı blobunun dönüştürmelerini anlatmak için kullanılır Q# .</span><span class="sxs-lookup"><span data-stu-id="d3ef3-126">Operations are used to describe the transformations of quantum systems and are the most fundamental building block of Q# programs.</span></span> <span data-ttu-id="d3ef3-127">İçinde tanımlanan her işlem, Q# diğer birkaç işlemi çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-127">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="d3ef3-128">İşlemlere karşılık işlevler, yalnızca *belirleyici* klasik davranışı betimleyen ve klasik değerleri hesaplama konusunda herhangi bir etkiye sahip olmayan işlevler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-128">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="d3ef3-129">Örneğin, bir programın sonundaki qubits 'i ölçmek istediğinizi ve ölçüm sonuçlarının bir diziye ekleneceğini varsayın.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-129">For example, suppose you want to measure the qubits at the end of a program and add the measurement results to an array.</span></span>
<span data-ttu-id="d3ef3-130">Bu durumda, `Measure` hedef makinenin (gerçek veya sanal) qubit üzerinde bir ölçü gerçekleştirmesini sağlayan bir *işlemdir* .</span><span class="sxs-lookup"><span data-stu-id="d3ef3-130">In this case, `Measure` is an *operation* that instructs the target machine to perform a measurement on the (real or simulated) qubits.</span></span> <span data-ttu-id="d3ef3-131">Aynı zamanda *işlevler* , döndürülen sonuçları bir diziye eklemek için klasik işlemi işler.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-131">At the same time, *functions* handle the classical process of adding the returned results to an array.</span></span>

<span data-ttu-id="d3ef3-132">Birlikte, işlemler ve işlevler *callables*olarak bilinir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-132">Together, operations and functions are known as *callables*.</span></span> <span data-ttu-id="d3ef3-133">Temel yapısı ve davranışları, [Içindeki Q# Işlemler ve işlevlerde ](xref:microsoft.quantum.guide.operationsfunctions)tanıtılmıştır ve ayrıntılıdır.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-133">Their underlying structure and behavior are introduced and detailed in [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>


## <a name="no-locq-syntax-overview"></a><span data-ttu-id="d3ef3-134">Q#sözdizimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="d3ef3-134">Q# syntax overview</span></span>

<span data-ttu-id="d3ef3-135">Bir dilin sözdizimi, sözdizimi doğru bir program oluşturan farklı sembol birleşimlerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-135">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="d3ef3-136">' De Q# , sözdizimi öğeleri üç farklı gruba sınıflandırılır: türler, ifadeler ve deyimler.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-136">In Q#, syntax elements are classified into three different groups: types, expressions, and statements.</span></span>

### <a name="types"></a><span data-ttu-id="d3ef3-137">Türler</span><span class="sxs-lookup"><span data-stu-id="d3ef3-137">Types</span></span>
<span data-ttu-id="d3ef3-138">Q#, türlerin iyi şekilde kullanılması derleyicinin derleme zamanında programlar hakkında güçlü garantiler sağlamasına yardımcı olabilir Q# .</span><span class="sxs-lookup"><span data-stu-id="d3ef3-138">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="d3ef3-139">Standart ve hisse özel yerleşik temel türlerin yanı sıra,,,, ve,,, `Int` , `Bool` `Qubit` ve, `Result` Q# Kullanıcı tanımlı türler için destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-139">In addition to standard and quantum-specific built-in primitive types, for example, `Int`, `Bool`, `Qubit`, and `Result`, Q# provides support for user-defined types.</span></span>

<span data-ttu-id="d3ef3-140">Tüm ilkel türlerin açıklamaları, dizi ve demet türlerine ilişkin ayrıntılar ve bir dosya içinde yeni türler tanımlama adımları için Q# , bkz. [türleri Q# ](xref:microsoft.quantum.guide.types).</span><span class="sxs-lookup"><span data-stu-id="d3ef3-140">For descriptions of all the primitive types, details for array and tuple types, and steps to define new types within a Q# file, see [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

### <a name="expressions"></a><span data-ttu-id="d3ef3-141">İfadeler</span><span class="sxs-lookup"><span data-stu-id="d3ef3-141">Expressions</span></span>
<span data-ttu-id="d3ef3-142">Programlama dilindeki bir ifade, programlama dilinin belirli bir değeri yorumlaması ve değerlendiren bir veya daha fazla sabitler, değişkenler, işleçler ve işlevlerin bir birleşimidir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-142">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="d3ef3-143">Çoğu durumda, bir dildeki her tür için, bu türdeki ifadeler, bu türdeki bir değere göre *değişmez* değer ya da semboller olabilir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-143">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="d3ef3-144">Örneğin, `5` bir değişmez değerdir `Int` (Bu nedenle türünde bir ifade `Int` ) ve sembol `count` tamsayı değerine bağlıysa, `5` `count` Ayrıca bir tamsayı ifadesi de olur.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-144">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="d3ef3-145">Ayrıca, bir ifade belirli işleçlerle birleştirilmiş diğer ifadelerden oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-145">Additionally, an expression can consist of other expressions combined by certain operators.</span></span>
<span data-ttu-id="d3ef3-146">Örneğin, `Int` olarak değerlendirilen başka bir ifade `5` `2+3` .</span><span class="sxs-lookup"><span data-stu-id="d3ef3-146">For example, another `Int` expression that evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="d3ef3-147">İçindeki ifadeler ve uyumlu işleçler hakkında daha fazla bilgi için Q# bkz. [ Q# içinde tür ifadeleri ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="d3ef3-147">For more information about expressions and compatible operators in Q#, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span> 

### <a name="statements"></a><span data-ttu-id="d3ef3-148">Deyimler</span><span class="sxs-lookup"><span data-stu-id="d3ef3-148">Statements</span></span> 
<span data-ttu-id="d3ef3-149">Bir ifade, gerçekleştirilecek bir eylemi ifade eden bir zorunlu programlama dilinin sözdizimsel birimidir. Bu deyimlerdeki ifadelerle karşıtlık ifadesi sonuçları döndürmez ve yalnızca yan etkileri için yürütülür.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-149">A statement is a syntactic unit of an imperative programming language that expresses some action to carry out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects.</span></span> <span data-ttu-id="d3ef3-150">Ancak, ifadesi her zaman bir sonuç döndürür ve genellikle yan etkileri yoktur.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-150">Expressions, however, always return a result and often do not have side effects at all.</span></span> <span data-ttu-id="d3ef3-151">Kısaca, Q# ifadeler değerlendirildiğinde deyimler yürütülür.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-151">In short, Q# statements are executed, while expressions are evaluated.</span></span>

<span data-ttu-id="d3ef3-152">İçindeki bir ifadeye basit bir örnek Q# , bir ifadeye sembol atanıyor:</span><span class="sxs-lookup"><span data-stu-id="d3ef3-152">A simple example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="d3ef3-153">Daha ilginç bir örnek, `for` yinelemeyi destekleyen ve bir *Ekstre bloğunu*içeren deyimdir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-153">A more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="d3ef3-154">`qubits`Bir qubits (Teknik olarak tür `Qubit[]` veya bir tür dizisi) kaydına yönelik simgenin olduğunu varsayalım `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="d3ef3-154">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, or an array of `Qubit` types).</span></span> <span data-ttu-id="d3ef3-155">Ardından</span><span class="sxs-lookup"><span data-stu-id="d3ef3-155">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="d3ef3-156">, kayıt sırasında her bir qubit üzerinde yinelenen bir ifadedir ve `H` her birinde işlem gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-156">is a statement that iterates over each qubit in the register, performing the `H` operation on each one.</span></span> <span data-ttu-id="d3ef3-157">Bunun de `H(qubit);` bir ifade olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-157">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="d3ef3-158">Türünde herhangi bir çağrı ifadesini kullanabilirsiniz `Unit` (bir `Unit` tür herhangi bir bilgi döndürmez), deyim olarak.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-158">You can use any call expression of type `Unit` (a `Unit` type does not return any information) as a statement.</span></span>
<span data-ttu-id="d3ef3-159">Bu tür bir ifade, `Unit` deyimin amacı örtülü hisse durumu değiştirmek olduğu için döndürülen qubits üzerinde işlemler çağrılırken faydalıdır.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-159">This type of expression is useful when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="d3ef3-160">İfade değerlendirme deyimleri, sonlandırma noktalı virgül gerektirir.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-160">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="d3ef3-161">Bir programın neredeyse her yönünü oluşturmak için deyimlerini kullanırsınız Q# ve bunlarla ilgili tüm bilgileri kapsayamaz.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-161">You use statements to build nearly every aspect of a Q# program, and no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="d3ef3-162">Kendi sözlü yapısı ve biçimlendirmesi hakkında daha fazla bilgi için bkz. [ Q# dosya yapısı](xref:microsoft.quantum.guide.filestructure); sembol bağlama ataması ve kapsamı için bkz. [içindeki Q# değişkenler ](xref:microsoft.quantum.guide.variables)ve gibi denetim akışı döngüleri için `for` , bkz. [Denetim akışı Q# ](xref:microsoft.quantum.guide.controlflow).</span><span class="sxs-lookup"><span data-stu-id="d3ef3-162">For more information about their lexical structure and formatting, see [Q# File Structure](xref:microsoft.quantum.guide.filestructure); for symbol binding assignment and scope, see [Variables in Q#](xref:microsoft.quantum.guide.variables); and for control flow loops such as `for`, see [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3ef3-163">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="d3ef3-163">Next steps</span></span>

<span data-ttu-id="d3ef3-164">[Içindeki Q# türler ](xref:microsoft.quantum.guide.types)hakkında öğrenmeye başlayın.</span><span class="sxs-lookup"><span data-stu-id="d3ef3-164">Start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="d3ef3-165">Arka plandaki temel bilgiler ve mosyon hakkında daha fazla bilgi için Q# bkz. [neden ihtiyacımız Q# var?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span><span class="sxs-lookup"><span data-stu-id="d3ef3-165">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
