---
title: 'S # temel kavramları'
description: 'Soru-cevap için temel kavramlar #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431164"
---
# <a name="q-basics"></a><span data-ttu-id="bf9c3-103">S # temel kavramları</span><span class="sxs-lookup"><span data-stu-id="bf9c3-103">Q# Basics</span></span>

<span data-ttu-id="bf9c3-104">Bu bölümde, Q # ' ın temel yapı taşlarına kısa bir giriş sunuyoruz.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-104">In this section we present a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="bf9c3-105">Ne olduğunu ve ne olduğuna ilişkin genel bir bakış için, hisse geliştirme setinin temel bir bileşeni olarak hangi noktada olduğunu ve [ne olduğunu](xref:microsoft.quantum.overview.q-sharp)öğrenmek için soru-cevap ' a bakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-105">For a quick overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, you can check out [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="bf9c3-106">Hisse bir program nedir?</span><span class="sxs-lookup"><span data-stu-id="bf9c3-106">What is a quantum program?</span></span>

<span data-ttu-id="bf9c3-107">Teknik açıdan, bir hisse bir program, çağrıldığında belirli işlemleri bir hisse sisteminde gerçekleştirirken belirli bir klasik alt yordamlar kümesi olarak görülebilir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-107">From a technical perspective, a quantum program can be seen as a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="bf9c3-108">Bu görünümün önemli bir sonucu, Q # dilinde yazılmış bir programın, qubits 'i doğrudan modelleyebilmesini, ancak klasik bir denetim bilgisayarının bu qubits ile nasıl etkileşime gireceğini açıklar.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-108">An important consequence of that view is that a program written in Q# does not directly model qubits themselves, but rather describes how a classical control computer interacts with those qubits.</span></span>
<span data-ttu-id="bf9c3-109">Tasarıma göre, soru-cevap, bu nedenle hisse veya diğer hisse ve diğer özellikleri doğrudan tanımlamaz.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-109">By design, Q# thus does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="bf9c3-110">Örneğin, hisse bilgi Işlem kavramları kılavuzunda $ \ket{+} = \left (\ket {0} + \ket {1} \ right)/\sqrt $ durumunu göz önünde bulundurun {2} . [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="bf9c3-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="bf9c3-111">Bu durumu Q # ' da hazırlamak için, qubits 'in $ \ket $ durumunda başlatıldığı olguları {0} ve $ \ket{+} = H\ket {0} $ olduğunu, burada $H $, [ `H` Operation] (] (XREF: Microsoft. hisse. Intrinsic. H) tarafından uygulanan Hadamard dönüşümünden kullanırız:</span><span class="sxs-lookup"><span data-stu-id="bf9c3-111">To prepare this state in Q#, we use the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the Hadamard transform, implemented by the [`H` operation](](xref:microsoft.quantum.intrinsic.h):</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a><span data-ttu-id="bf9c3-112">Soru-cevap durumu #</span><span class="sxs-lookup"><span data-stu-id="bf9c3-112">Quantum states in Q#</span></span>

<span data-ttu-id="bf9c3-113">Daha da, yukarıdaki programın yazılmasında, Q # içindeki duruma açıkça başvurmuyoruz, ancak durumun programımız tarafından nasıl *dönüştürüldüğünü* açıklıyoruz.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-113">Importantly, in writing the above program, we did not explicitly refer to the state within Q#, but rather described how the state was *transformed* by our program.</span></span>
<span data-ttu-id="bf9c3-114">Bu, makineye bağlı farklı yorumlamalar olabilecek her bir hedef makinede bile her bir hisse alım durumunun büyük bir yerde *olduğu* konusunda tamamen belirsiz bir durumdur.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-114">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="bf9c3-115">Bir Q # programı bir qubit 'in durumuna introspect bir özelliğine sahip değildir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-115">A Q# program has no ability to introspect into the state of a qubit.</span></span>
<span data-ttu-id="bf9c3-116">Bunun yerine, bir program [`Measure`](xref:microsoft.quantum.intrinsic.measure) qubit 'ten bilgi almak için gibi işlemleri çağırabilir ve [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) bir qubit durumu üzerinde işlem yapmak için ve gibi işlemleri çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-116">Rather, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="bf9c3-117">Bu *işlemlerin gerçekten ne* olduğunu yalnızca belirli bir Q # programını çalıştırmak için kullandığımız hedef makine tarafından somut hale getirilir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-117">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>
<span data-ttu-id="bf9c3-118">Örneğin, programı [tam durum benzeticimizde](xref:microsoft.quantum.machines.full-state-simulator)çalıştırırsanız simülatör, sanal hisse sisteme karşılık gelen matematiksel işlemleri yapar.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-118">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator will perform the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="bf9c3-119">Ancak geleceğe bakıyorum, hedef makine gerçek bir hisse bilgisayar olduğunda, Q # ' da bu gibi işlemleri çağırmak, hisse bilgisayarını *Gerçek* hisse sisteminde ilgili *gerçek* işlemleri gerçekleştirmeye yönlendirir (örneğin, tam olarak süreli lazer pulu).</span><span class="sxs-lookup"><span data-stu-id="bf9c3-119">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="bf9c3-120">Bir Q # programı, Express hisse hesaplamasına yeni ve daha üst düzey işlemler oluşturmak için bu işlemleri bir hedef makine tarafından tanımlanan şekilde yeniden birleştirir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-120">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="bf9c3-121">Bu şekilde, Q #, temel alınan hisse ve hibrit, klasik algoritmaların yanı sıra bir hedef makine ya da simülatör yapısına göre genel de olacak şekilde ifade yapmayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-121">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="bf9c3-122">S # işlem ve işlevleri</span><span class="sxs-lookup"><span data-stu-id="bf9c3-122">Q# operations and functions</span></span>

<span data-ttu-id="bf9c3-123">Bir Q # programı, *işlemlerden*, *işlevlerden*ve Kullanıcı tanımlı türlerden oluşur.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-123">Concretely, a Q# program is comprised of *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="bf9c3-124">İşlemler, hisse sistemleri dönüştürmelerini ve en temel yapı bloğu olan Q # programlarını anlatmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-124">Operations are used to describe the transformations of quantum systems and are the most basic building block of Q# programs.</span></span> <span data-ttu-id="bf9c3-125">Q # içinde tanımlanan her işlem, diğer birkaç işlemi çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-125">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="bf9c3-126">İşlemlere karşılık işlevler, yalnızca *belirleyici* klasik davranışı betimleyen ve klasik değerleri hesaplama konusunda herhangi bir etkiye sahip olmayan işlevler için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-126">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="bf9c3-127">Örneğin, bir programın sonunda qubits 'lerimizi ölçmek istiyoruz ve ölçüm sonuçlarını bir diziye ekleyin.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-127">For example, suppose we would like to measure our qubits at the end of a program, and add the measurement results to an array.</span></span>
<span data-ttu-id="bf9c3-128">Bu durumda, `Measure` hedef makinenin (gerçek veya sanal) qubit üzerinde bir ölçüm gerçekleştirmesini bildiren bir *işlemdir* ve döndürülen sonuçların bir diziye eklenmesi, bu işlemler *işlevleri*tarafından işlenir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-128">In this case `Measure` is an *operation* which instructs the target machine to perform a measurement on the (real or simulated) qubits, and the classical process of adding the returned results to an array will be handled by *functions*.</span></span>

<span data-ttu-id="bf9c3-129">Birlikte, işlemler ve işlevler *callables*olarak adlandırılır ve temel yapısı ve davranışları [Q # sayfasındaki işlemler ve işlevlerde](xref:microsoft.quantum.guide.operationsfunctions) tanıtılmıştır.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-129">Together, operations and functions are referred to as *callables*, and their underlying structure and behavior is introduced on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) page.</span></span>


## <a name="q-syntax-overview"></a><span data-ttu-id="bf9c3-130">S # sözdizimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="bf9c3-130">Q# syntax overview</span></span>

<span data-ttu-id="bf9c3-131">Bir dilin sözdizimi, sözdizimi doğru bir program oluşturan farklı sembol birleşimlerini tanımlar.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-131">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="bf9c3-132">Q # içinde, söz dizimi öğelerini üç farklı grupta sınıflandırabilir: türler, ifadeler ve deyimler.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-132">In Q# we can classify the elements of its syntax in three different groups: types, expressions and statements.</span></span>

### <a name="types"></a><span data-ttu-id="bf9c3-133">Türler</span><span class="sxs-lookup"><span data-stu-id="bf9c3-133">Types</span></span>
<span data-ttu-id="bf9c3-134">S #, türlerin dikkatli kullanımı derleyicinin derleme zamanında Q # programları hakkında güçlü garantiler sağlamasına yardımcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-134">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="bf9c3-135">Standart ve hisse özel yerleşik temel türlerin yanı sıra (örn.,, `Int` `Bool` `Qubit` ve `Result` ), Q # Kullanıcı tanımlı türler için destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-135">In addition to standard and quantum-specific built-in primitive types (e.g. `Int`, `Bool`, `Qubit`, and `Result`), Q# provides support for user-defined types.</span></span>
<span data-ttu-id="bf9c3-136">Tüm Q # ve temel türler, dizi ve demet türlerindeki ayrıntıların yanı sıra, bir Q # dosyası içinde yeni türlerin tanımlanması ile birlikte Q # sayfasındaki [türler](xref:microsoft.quantum.guide.types) üzerinde açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-136">All of Q#'s various primitive types are described on the [Types in Q#](xref:microsoft.quantum.guide.types) page, along with details on array and tuple types, as well as how to define new types within a Q# file.</span></span>

### <a name="expressions"></a><span data-ttu-id="bf9c3-137">İfadeler</span><span class="sxs-lookup"><span data-stu-id="bf9c3-137">Expressions</span></span>
<span data-ttu-id="bf9c3-138">Programlama dilindeki bir ifade, programlama dilinin belirli bir değeri yorumlaması ve değerlendiren bir veya daha fazla sabitler, değişkenler, işleçler ve işlevlerin bir birleşimidir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-138">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="bf9c3-139">Çoğu durumda, bir dildeki her tür için, bu türdeki ifadeler, bu türdeki bir değere göre *değişmez* değer ya da semboller olabilir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-139">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="bf9c3-140">Örneğin, `5` bir değişmez değerdir `Int` (Bu nedenle türünde bir ifade `Int` ) ve sembol `count` tamsayı değerine bağlıysa, `5` `count` Ayrıca bir tamsayı ifadesi de olur.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-140">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="bf9c3-141">Ayrıca, bir ifade belirli işleçlerle birleştirilmiş diğer ifadelerden oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-141">Additionally, an expression can consist of other expressions combined with certain operators.</span></span>
<span data-ttu-id="bf9c3-142">Bu nedenle `Int` , olduğunu değerlendiren bir ifadenin başka bir `5` örneği `2+3` .</span><span class="sxs-lookup"><span data-stu-id="bf9c3-142">Hence another example of an `Int` expression which evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="bf9c3-143">Q # içindeki türlerin olası ifadeleri ve bunları oluşturmak için kullanılabilecek uyumlu işleçler, [q # sayfasındaki tür ifadelerinde](xref:microsoft.quantum.guide.expressions) ayrıntılıdır.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-143">The possible expressions of types in Q#, as well as the compatible operators that can be used to form them, are detailed on the [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) page.</span></span> 

### <a name="statements"></a><span data-ttu-id="bf9c3-144">Deyimler</span><span class="sxs-lookup"><span data-stu-id="bf9c3-144">Statements</span></span> 
<span data-ttu-id="bf9c3-145">Bir ifade, gerçekleştirilecek eylemi belirten bir zorunlu programlama dilinin sözdizimsel birimidir. Bu deyimlerdeki ifadelerle karşıtlık ifadesi, sonuçları döndürmez ve yalnızca yan etkileri için yürütülür, ancak ifadeler her zaman bir sonuç döndürür ve genellikle yan etkileri yoktur.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-145">A statement is a syntactic unit of an imperative programming language that expresses some action to be carried out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects, while expressions always return a result and often do not have side effects at all.</span></span>
<span data-ttu-id="bf9c3-146">Bu ayrım genellikle, ifadesi içinde gözlemlenmiştir: bir ifade değerlendirilir, ancak bir deyim yürütülür.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-146">This distinction is frequently observed in wording: an expression is evaluated, whereas a statement is executed.</span></span>

<span data-ttu-id="bf9c3-147">Q # içindeki bir deyimin çok temel bir örneği bir ifadeye sembol atamaktır:</span><span class="sxs-lookup"><span data-stu-id="bf9c3-147">A very basic example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="bf9c3-148">`for`Yineleme destekleyen ve bir *Ekstre bloğunu*içeren deyimde biraz daha ilginç bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-148">A slightly more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="bf9c3-149">Varsayalım ki, `qubits` bir qubits kaydına (Teknik olarak tür dizisi) bağladır `Qubit[]` `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="bf9c3-149">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, i.e. an array of `Qubit` types).</span></span> <span data-ttu-id="bf9c3-150">Ardından</span><span class="sxs-lookup"><span data-stu-id="bf9c3-150">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="bf9c3-151">, kayıt sırasında her bir qubit üzerinde yinelenen bir ifadedir ve `H` her birinde işlem gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-151">is a statement which iterates over each qubit in the register, performing the `H` operation on each.</span></span> <span data-ttu-id="bf9c3-152">Bunun de `H(qubit);` bir ifade olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-152">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="bf9c3-153">Aslında, türünde herhangi bir çağrı ifadesi `Unit` (herhangi bir bilgi döndürmeyen bu callables) bir deyim olarak kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-153">In fact, any call expression of type `Unit` (those callables that do not return any information) may be used as a statement.</span></span>
<span data-ttu-id="bf9c3-154">Bu, `Unit` deyimin amacı örtülü hisse durumu ' nu değiştirecek olduğundan, bu işlem öncelikli olarak döndürülen qubits 'teki işlemleri çağırırken kullanılır.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-154">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="bf9c3-155">İfade değerlendirme deyimleri, sonlandırma noktalı virgül gerektirir.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-155">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="bf9c3-156">Bir Q # programının neredeyse her yönü, using deyimleri kullanılarak oluşturulmuştur, bu nedenle bunlarla ilgili tüm bilgileri kapsayamaz.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-156">Nearly every aspect of a Q# program is built using statements, so no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="bf9c3-157">Ancak, kendi sözlü yapısı ve biçimlendirmesi, q # [dosya yapısı](xref:microsoft.quantum.guide.filestructure) sayfasında, soru-cevap atama ve q [# içindeki değişkenlerde](xref:microsoft.quantum.guide.variables)kapsam ve `for` [q # içindeki denetim akışı](xref:microsoft.quantum.guide.controlflow)gibi denetim akışı döngülerinde açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-157">However, their lexical structure and formatting is described on the [Q# File Structure](xref:microsoft.quantum.guide.filestructure) page, symbol binding assignment and scope at [Variables in Q#](xref:microsoft.quantum.guide.variables), and control flow loops such as `for` at [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>


## <a name="whats-next"></a><span data-ttu-id="bf9c3-158">Sırada ne var?</span><span class="sxs-lookup"><span data-stu-id="bf9c3-158">What's next?</span></span>
<span data-ttu-id="bf9c3-159">Bu kılavuzun geri kalanında, işlem, işlev ve türlerin temel yapı taşları aracılığıyla karmaşık hisse programları oluşturmak için Q # ' ı nasıl kullanacağınızı göstereceğiz.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-159">Throughout the rest of this guide, we will show you how to use Q# to construct complex quantum programs through the basic building blocks of operations, functions, and types.</span></span>

<span data-ttu-id="bf9c3-160">Başlamak için, [Q # Içinde türler](xref:microsoft.quantum.guide.types)hakkında öğrenmeye başlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-160">To get started, you can start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="bf9c3-161">Soru-cevap hakkında daha fazla bilgi edinmek istiyorsanız, soru-cevap ' ı [neden ihtiyacım var?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)' i inceleyin.</span><span class="sxs-lookup"><span data-stu-id="bf9c3-161">If you are interested in learning more about the foundations and motivation behind Q#, check out [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
