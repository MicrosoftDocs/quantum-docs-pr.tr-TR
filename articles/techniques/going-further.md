---
title: Daha fazla soru-Q-Teknik | Microsoft Docs
description: 'Daha fazla soru-Q # Teknik'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.going-further
ms.openlocfilehash: bd2b799d4001e280baccb04158247891b9cbb5bc
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820207"
---
# <a name="going-further"></a><span data-ttu-id="cfd70-103">Daha fazla</span><span class="sxs-lookup"><span data-stu-id="cfd70-103">Going Further</span></span> #

<span data-ttu-id="cfd70-104">Artık soru-cevap programlarının soru-cevap olarak nasıl yazılacağını gördüğünüze göre, bu bölüm ileride yararlı olması için daha fazla gelişmiş konu sunarak daha fazla bilgi edinilerek devam ediyor.</span><span class="sxs-lookup"><span data-stu-id="cfd70-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="cfd70-105">Genel Işlemler ve Işlevler</span><span class="sxs-lookup"><span data-stu-id="cfd70-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="cfd70-106">Bu bölümde, diğer dillerdeki [genel C#türler ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [, F# ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++ şablonlarda, şablonlar](https://docs.microsoft.com/cpp/cpp/templates-cpp)veya diğer dillerde metaprogramlamaya benzer yaklaşımlar içeren bazı temel benzerlik varsayılmaktadır.</span><span class="sxs-lookup"><span data-stu-id="cfd70-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="cfd70-107">Tanımlamak isteyebileceğiniz birçok işlev ve işlem, kendi giriş türlerine gerçekten büyük ölçüde güvenmiyor, ancak bunun yerine yalnızca başka bir işlev veya işlem aracılığıyla türlerini örtülü olarak kullanın.</span><span class="sxs-lookup"><span data-stu-id="cfd70-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="cfd70-108">Örneğin, yaygın olarak kullanılan *harita* kavramını birçok işlevsel dilde değerlendirin. $f (x) $ işlevi ve $\{x_1, x_2, \noktalar, x_n\}$, Map bir değer koleksiyonu verildiğinde, <\{f (x_1), f (x_2), \noktalar, f (x_n)\}$ gibi yeni bir koleksiyon döndürür.</span><span class="sxs-lookup"><span data-stu-id="cfd70-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="cfd70-109">Bunu Q # ' da uygulamak için, bu işlevlerden faydalanabilir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="cfd70-110">İhtiyaç duyduğumuz türleri anlarken, bir yer tutucu olarak ★ kullanarak `Map`hızlı bir örneğini yazalım.</span><span class="sxs-lookup"><span data-stu-id="cfd70-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="cfd70-111">Bu işlev, yaptığımız gerçek türler dikkate alınmaz.</span><span class="sxs-lookup"><span data-stu-id="cfd70-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="cfd70-112">Örneğin, tamsayılardan Paulis 'e yapılan bir harita, kayan noktalı sayıların dizelerdeki eşlemesiyle çok benzer şekilde görünür:</span><span class="sxs-lookup"><span data-stu-id="cfd70-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="cfd70-113">Prensibi, karşılaştiğimiz her tür çifti için `Map` bir sürümünü yazalım, ancak bu çok sayıda zorluklar sunarız.</span><span class="sxs-lookup"><span data-stu-id="cfd70-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="cfd70-114">Örneğin, `Map`bir hata bulduk, bu durumda düzeltilmesinin tüm `Map`sürümlerinde tek bir şekilde uygulandığından emin olunması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="cfd70-115">Ayrıca, yeni bir tanımlama grubu veya UDT oluşturuyoruz, yeni tür ile birlikte çalışmak için yeni bir `Map` de oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="cfd70-116">Bu, az sayıda işlev için daha fazla ve daha fazla `Map`işlev topladığımızda, bu tür bir izleme tablosu olsa da, yeni türleri tanıtma maliyeti oldukça kısa bir süre boyunca makul bir şekilde büyük hale gelir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="cfd70-117">Bununla birlikte, bu zorluklar, derleyicinin farklı `Map` sürümlerinin birbirleriyle ilgili olduğunu tanıması için ihtiyaç duymadığımızda oluşur.</span><span class="sxs-lookup"><span data-stu-id="cfd70-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="cfd70-118">Etkin olarak, derleyicinin `Map` bir tür matematik işlevini Q # *türünden* q # işlevlerine kadar görmesini istiyoruz.</span><span class="sxs-lookup"><span data-stu-id="cfd70-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="cfd70-119">Bu kavram, işlevlerin ve işlemlerin *tür parametrelerine*ve bunların normal demet parametrelerine sahip olmasını sağlayarak şekillendirililir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="cfd70-120">Yukarıdaki örneklerde, ilk durumda `Int, Pauli` tür parametrelerine sahip olarak `Map` düşünmek istiyoruz ve ikinci durumda `Double, String`.</span><span class="sxs-lookup"><span data-stu-id="cfd70-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="cfd70-121">Çoğu bölüm için, bu tür parametreleri normal türlermiş gibi kullanılabilir: dizileri ve tanımlama grupları oluşturmak, işlevleri ve işlemleri çağırmak ve sıradan ya da kesilebilir değişkenlere atamak için parametre türü değerlerini kullanıyoruz.</span><span class="sxs-lookup"><span data-stu-id="cfd70-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="cfd70-122">Dolaylı bağımlıların en büyük olması, bir Q # programının `Qubit` türünün yapısına doğrudan güvenebileceği, ancak bu tür türleri diğer işlemlere ve işlevlere geçirmesi **gereken** qubitlerdir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="cfd70-123">Yukarıdaki örneğe dönerek, bir tane olmak üzere tür parametrelerine sahip olmak için `Map` gerektiğini ve bir diğeri de `fn`çıktıyı temsil edecek şekilde `fn`.</span><span class="sxs-lookup"><span data-stu-id="cfd70-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="cfd70-124">Q # dilinde, bu, bildiriminde bir işlev veya işlemin adından sonra ve her tür parametresini listeleyerek açılı ayraç (brakets $ \bratus{}$! değil `<>`) eklenerek yazılır.</span><span class="sxs-lookup"><span data-stu-id="cfd70-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="cfd70-125">Her tür parametresinin adı, bir tür parametresi olduğunu ve sıradan bir tür ( *somut* tür olarak da bilinir) olmadığını belirten bir Tick `'`ile başlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="cfd70-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="cfd70-126">`Map`için şunu yazın:</span><span class="sxs-lookup"><span data-stu-id="cfd70-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="cfd70-127">`Map<'Input, 'Output>` tanımının, daha önce yazdığımız sürümlere çok benzediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="cfd70-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="cfd70-128">Tek fark, derleyicinin `Map` `'Input` ve `'Output` ne olduğunu doğrudan belirtmediğimiz, ancak bunları `fn`aracılığıyla dolaylı olarak kullanarak herhangi iki tür için nasıl çalıştığına dair kesin olarak bilgi sahibi veriyoruz.</span><span class="sxs-lookup"><span data-stu-id="cfd70-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="cfd70-129">Bu şekilde `Map<'Input, 'Output>` tanımladıktan sonra, bu işlemi sıradan bir fonksiyonmuş gibi çağırabiliriz:</span><span class="sxs-lookup"><span data-stu-id="cfd70-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="cfd70-130">Genel işlevler ve işlemler yazmak, "kayıt düzeni-Out" ın Q # işlevleri ve işlemlerini düşünmek için çok faydalı bir yoldur.</span><span class="sxs-lookup"><span data-stu-id="cfd70-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="cfd70-131">Her işlev tam olarak bir giriş yaptığından ve tam olarak bir çıkış döndürdüğünden, `'T -> 'U` türünde bir giriş *herhangi* bir Q # işleviyle eşleşir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="cfd70-132">Benzer şekilde, herhangi bir işlem `'T => 'U`türünde bir girişe geçirilebilir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="cfd70-133">İkinci bir örnek olarak, iki diğer işlevin birleşimini döndüren bir işlev yazma sınamasını göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="cfd70-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="cfd70-134">Burada, tam olarak hangi `A`, `B`ve `C` olduğunu belirtmemiz gerekir. bu nedenle, yeni `Compose` işlevimizin yardımcı programını ciddi ölçüde kısıtlar.</span><span class="sxs-lookup"><span data-stu-id="cfd70-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="cfd70-135">Tüm `Compose`, yalnızca `A`, `B`ve `C` `innerFn` ve `outerFn`*aracılığıyla* bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="cfd70-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="cfd70-136">Alternatif olarak *, `A`,* `B`ve `C`için çalıştığını belirten `Compose` tür parametreleri ekleyebiliyoruz, böylece bu parametreler `innerFn` ve `outerFn`tarafından beklenen olanlarla eşleşir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="cfd70-137">Q # standart kitaplıkları, daha yüksek sıralı denetim akışı hızlı bir şekilde daha kolay hale getirmek için tür parametreli işlem ve işlev aralığı sağlar.</span><span class="sxs-lookup"><span data-stu-id="cfd70-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="cfd70-138">Bunlar, [Q # standart kitaplığı kılavuzunda](xref:microsoft.quantum.libraries.standard.intro)daha ayrıntılı olarak ele alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="cfd70-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="cfd70-139">Ödünç alma qubit</span><span class="sxs-lookup"><span data-stu-id="cfd70-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="cfd70-140">Ödünç alma mekanizması, bir hesaplama sırasında karalama alanı olarak kullanılabilecek qubits ayrılmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="cfd70-141">Bu qubits genellikle temiz bir durumda değildir, yani $ \ket{0}$ gibi bilinen bir durumda başlatılmazlar.</span><span class="sxs-lookup"><span data-stu-id="cfd70-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="cfd70-142">Ayrıca, durumu bilinmediği için "kirli" qubit "de konuşur ve hatta hisse bilgisayar belleğinin diğer bölümleriyle de bir arada olabilir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="cfd70-143">Kirli qubits 'in bilinen kullanım durumları arasında, yalnızca çok az sayıda qubit ve incrementers uygulaması gerektiren çok kontrollü CNOT kapıları olan uygulamalardır.</span><span class="sxs-lookup"><span data-stu-id="cfd70-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="cfd70-144">Canon 'de, aşağıda tanımlanan işlev `MultiControlledXBorrow` gibi `borrowing` anahtar sözcüğünü kullanan örnekler vardır.</span><span class="sxs-lookup"><span data-stu-id="cfd70-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="cfd70-145">`controls`, bir `X` işlemine eklenmesi gereken denetim qubits ' i alıyorsa, bu uygulama tarafından `Length(controls)-2` çok sayıda kirli ve bu şekilde bir genel bakış eklenir.</span><span class="sxs-lookup"><span data-stu-id="cfd70-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="cfd70-146">`With`---Combinator ' nin, adjoint 'i destekleyen işlemler için geçerli olan `WithA`---, bu örnekte, `With` içeren yapılara denetim ekleme ve yalnızca denetimi iç işleme yayar.</span><span class="sxs-lookup"><span data-stu-id="cfd70-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="cfd70-147">İşlemin `body` ek olarak, işlemin `controlled` gövdesinin bir `controlled auto` bildirimine yeniden eklemek yerine açıkça sağlandığını daha fazla unutmayın.</span><span class="sxs-lookup"><span data-stu-id="cfd70-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="cfd70-148">Bunun nedeni, her bir ve `body`her bir kapıya denetim eklemeye kıyasla yararlı olan daha fazla denetimi nasıl kolayca ekleyebileceğinizi biliyoruz.</span><span class="sxs-lookup"><span data-stu-id="cfd70-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="cfd70-149">Bu kodu, `using` mekanizması kullanılarak birkaç temiz qubit kullanan, çarpma denetimli `X` işlemi uygulama amacını elde eden başka bir Canon işlevi `MultiControlledXClean` karşılaştırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="cfd70-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
