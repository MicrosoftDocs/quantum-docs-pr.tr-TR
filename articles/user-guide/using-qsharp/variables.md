---
title: 'Soru-cevap #'
description: Fill açıklaması
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430909"
---
# <a name="variables-in-q"></a><span data-ttu-id="f1517-103">Soru-cevap #</span><span class="sxs-lookup"><span data-stu-id="f1517-103">Variables in Q#</span></span>

<span data-ttu-id="f1517-104">S #, değişebilir ve değişmez semboller arasında veya deyimlere sınırlanan/atanan "değişkenler" arasında ayrım yapar.</span><span class="sxs-lookup"><span data-stu-id="f1517-104">Q# distinguishes between mutable and immutable symbols, or "variables", which are bound/assigned to expressions.</span></span>
<span data-ttu-id="f1517-105">Genellikle, derleyicinin daha iyi iyileştirmeler gerçekleştirmesini sağladığından, değişmez sembollerin kullanılması önerilir.</span><span class="sxs-lookup"><span data-stu-id="f1517-105">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="f1517-106">Bir bağlamanın sol tarafı bir sembol tanımlama grubu ve bir ifadenin sağ tarafından oluşur.</span><span class="sxs-lookup"><span data-stu-id="f1517-106">The left-hand-side of a binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

## <a name="immutable-variables"></a><span data-ttu-id="f1517-107">Sabit değişkenler</span><span class="sxs-lookup"><span data-stu-id="f1517-107">Immutable Variables</span></span>

<span data-ttu-id="f1517-108">Q # içindeki herhangi bir türde bir değer, anahtar sözcüğü kullanılarak bir işlem veya işlev içinde yeniden kullanım için bir değişkene atanabilir `let` .</span><span class="sxs-lookup"><span data-stu-id="f1517-108">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>

<span data-ttu-id="f1517-109">Değişmez bir bağlama anahtar sözcükten `let` , ardından bir sembol veya sembol kümesi, eşittir işareti `=` , sembolleri bağlamak için bir ifade ve sondaki noktalı virgülden oluşur.</span><span class="sxs-lookup"><span data-stu-id="f1517-109">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="f1517-110">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="f1517-110">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="f1517-111">Bu, belirli bir Pauli işleçleri dizisini değişken adına (veya "Symbol") atar `measurementOperator` .</span><span class="sxs-lookup"><span data-stu-id="f1517-111">This assigns a particular array of Pauli operators to the variable name (or "symbol"), `measurementOperator`.</span></span>

> [!NOTE]
> <span data-ttu-id="f1517-112">Deyimin sağ tarafındaki ifade `let` belirsiz olduğundan ve tür derleyici tarafından çıkarsandığı için yeni değişkenimizin türünü açıkça belirtmemiz gerekmedik.</span><span class="sxs-lookup"><span data-stu-id="f1517-112">We did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="f1517-113">Kullanılarak tanımlanan değişkenler `let` *sabittir*, yani tanımlandıktan sonra hiçbir şekilde değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="f1517-113">Variables defined using `let` are *immutable*, meaning that once it has been defined, it can no longer be changed in any way.</span></span>
<span data-ttu-id="f1517-114">Bu, bir işlemin türevini uygulamak için değişkenlerin yeniden düzenlenmesine yönelik klasik mantığın iyileştirilmesi dahil olmak üzere birkaç yarar iyileştirmesi sağlar `Adjoint` .</span><span class="sxs-lookup"><span data-stu-id="f1517-114">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

## <a name="mutable-variables"></a><span data-ttu-id="f1517-115">Değişebilir değişkenler</span><span class="sxs-lookup"><span data-stu-id="f1517-115">Mutable Variables</span></span>

<span data-ttu-id="f1517-116">İle bir değişken oluşturulmasına alternatif olarak `let` , anahtar sözcüğü, `mutable` ilk oluşturulduktan sonra anahtar sözcüğü kullanılarak oluşturulduktan *can* sonra yeniden bağlanabilen kesilebilir bir değişken oluşturur `set` .</span><span class="sxs-lookup"><span data-stu-id="f1517-116">As an alternative to creating a variable with `let`, the `mutable` keyword will create a mutable variable that *can* be re-bound after it is initially created by using the `set` keyword.</span></span>

<span data-ttu-id="f1517-117">Bir deyimin parçası olarak belirtilen ve bağlantılı semboller `mutable` kodun ilerleyen kısımlarında farklı bir değere yeniden bağlanabilir.</span><span class="sxs-lookup"><span data-stu-id="f1517-117">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> <span data-ttu-id="f1517-118">Bir sembol kodun ilerleyen kısımlarında yeniden bağlanmışsa, türü değişmez ve yeni bağlanan değerin bu türle uyumlu olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="f1517-118">If a symbol is rebound later in the code, its type does not change, and the newly bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="f1517-119">Kesilebilir sembolleri yeniden bağlama</span><span class="sxs-lookup"><span data-stu-id="f1517-119">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="f1517-120">Kesilebilir değişken, bir ifade kullanılarak yeniden bağlanabilir `set` .</span><span class="sxs-lookup"><span data-stu-id="f1517-120">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="f1517-121">Bu tür bir yeniden bağlama anahtar sözcüğünden `set` , ardından bir sembol veya sembol tanımlama grubu, eşittir işareti `=` , sembolleri yeniden bağlamak için bir ifade ve sondaki noktalı virgülden oluşur.</span><span class="sxs-lookup"><span data-stu-id="f1517-121">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>

<span data-ttu-id="f1517-122">Burada, yeniden bağlama bildiriminin tekniklerinin bazı örneklerini sunuyoruz</span><span class="sxs-lookup"><span data-stu-id="f1517-122">Here, we provide some possible examples of rebinding statement techniques</span></span>

### <a name="apply-and-reassign-statements"></a><span data-ttu-id="f1517-123">Uygula ve yeniden ata deyimleri</span><span class="sxs-lookup"><span data-stu-id="f1517-123">Apply-and-Reassign Statements</span></span>

<span data-ttu-id="f1517-124">`set`Bir *Apply ve-reassıgn* olarak ifade edilen belirli bir tür ifade, sağ taraftaki bir ikili işleç uygulamasından oluşuyorsa ve sonucun işlecin sol bağımsız değişkenine yeniden bağlanması durumunda bir birleştirme için kullanışlı bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="f1517-124">A particular kind of `set`-statement we refer to as an *apply-and-reassign* statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="f1517-125">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="f1517-125">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="f1517-126">`counter`döngünün her yinelemesinde sayacın değerini artırır `for` .</span><span class="sxs-lookup"><span data-stu-id="f1517-126">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="f1517-127">Yukarıdaki kod şu şekilde eşdeğerdir</span><span class="sxs-lookup"><span data-stu-id="f1517-127">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

<span data-ttu-id="f1517-128">Benzer deyimler, sol taraftaki türün ifade türüyle eşleştiği tüm ikili işleçler için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f1517-128">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="f1517-129">Bu, örneğin değerleri biriktirmek için kullanışlı bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="f1517-129">This provides for example a convenient way to accumulate values.</span></span>

<span data-ttu-id="f1517-130">Örneğin, `qubits` bir Quu 'nin bir REGOF:</span><span class="sxs-lookup"><span data-stu-id="f1517-130">For example, supposing `qubits` is a regsiter of qubits:</span></span>
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a><span data-ttu-id="f1517-131">Güncelleştirme ve yeniden atama deyimleri</span><span class="sxs-lookup"><span data-stu-id="f1517-131">Update-and-Reassign Statements</span></span>

<span data-ttu-id="f1517-132">Sağ taraftaki [kopyalama ve güncelleştirme ifadeleri](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) için benzer bir birleştirme bulunur.</span><span class="sxs-lookup"><span data-stu-id="f1517-132">A similar concatenation exists for [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) on the right-hand-side.</span></span>
<span data-ttu-id="f1517-133">Kullanıcı tanımlı türlerde ve *dizi öğelerinde* *adlandırılmış öğeler* için birlikte, *Update-ve-yeniden ata* deyimleri mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="f1517-133">Correspondingly, *update-and-reassign* statements exist for *named items* in user-defined types as well as for *array items*.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="f1517-134">Diziler söz konusu olduğunda, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) Standart kitaplıklarımızda birçok yaygın dizi başlatma ve işleme ihtiyacı için gerekli araçları sağlar ve bu nedenle dizi öğelerini ilk yerde güncelleştirmek zorunda kalmamak için yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="f1517-134">In the case of arrays, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) in our standard libraries provides the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> 

<span data-ttu-id="f1517-135">Update-ve-yeniden ata deyimleri gerekirse bir alternatif sağlar:</span><span class="sxs-lookup"><span data-stu-id="f1517-135">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

<span data-ttu-id="f1517-136">' De sağlanan diziler için kitaplık araçlarını kullanarak, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) Örneğin, dizinindeki `i` pabd'ın verilen değeri aldığı ve diğer tüm girdilerin kimlik olduğu Paulis dizisini döndüren bir işlevi kolayca tanımlayabiliriz.</span><span class="sxs-lookup"><span data-stu-id="f1517-136">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can, for example, easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity.</span></span>

<span data-ttu-id="f1517-137">Bu tür bir işlevin, elden çıkarmada araçların avantajlarından faydalanarak iki tanımı vardır.</span><span class="sxs-lookup"><span data-stu-id="f1517-137">Here are two definitions of such a function, with the second taking advantage of the tools at our disposal.</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

<span data-ttu-id="f1517-138">Dizideki her bir dizin üzerinde yineleme yapmak yerine, veya ' i koşullu olarak ayarlamak `PauliI` yerine `Pauli` `ConstantArray` ' den ' ı kullanarak [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) ' ın bir dizisini oluşturup `PauliI` , sonra dizinde belirtilen değer c değerini değiştirdiğimiz bir kopya ve güncelleştirme ifadesini döndürmemiz gerekir `location` :</span><span class="sxs-lookup"><span data-stu-id="f1517-138">Instead of iterating over each index in the array, and conditionally setting it to `PauliI` or `Pauli`, we can instead use `ConstantArray` from [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) to create an array of `PauliI`'s, and then simply returning a copy-and-update expression in which we've changed the specifc value at index `location`:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a><span data-ttu-id="f1517-139">Demet oluşturmayı kaldırma</span><span class="sxs-lookup"><span data-stu-id="f1517-139">Tuple Deconstruction</span></span>

<span data-ttu-id="f1517-140">Tek bir değişken atamaya ek olarak, `let` ve `mutable` anahtar sözcükler (aşağıda açıklanan---) gibi diğer tüm bağlama yapısına de---, `set` Ayrıca bir [demet türünün](xref:microsoft.quantum.guide.types#tuple-types)içeriğinin açılmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="f1517-140">In addition to assigning a single variable, the `let` and `mutable` keywords---or in fact any other binding construct, such as `set` (described below)---also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.guide.types#tuple-types).</span></span>
<span data-ttu-id="f1517-141">Bu formun bir ataması, bu kayıt düzeninin öğelerini *parçalara ayırmayı* kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="f1517-141">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>

<span data-ttu-id="f1517-142">Bağlamanın sağ tarafı bir tanımlama grubu ise, bu kayıt düzeni atama sonrasında oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="f1517-142">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="f1517-143">Bu tür ayrıştırmaları iç içe geçmiş tanımlama gruplarını içerebilir ve sağ taraftaki tanımlama grubunun şekli sembol tanımlama grubu şekli ile uyumlu olduğu sürece herhangi bir tam veya kısmi kaldırma geçerli olur.</span><span class="sxs-lookup"><span data-stu-id="f1517-143">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>

<span data-ttu-id="f1517-144">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="f1517-144">For example:</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a><span data-ttu-id="f1517-145">Kapsamları bağlama</span><span class="sxs-lookup"><span data-stu-id="f1517-145">Binding Scopes</span></span>

<span data-ttu-id="f1517-146">Genel olarak, sembol bağlamaları kapsam dışına çıkar ve içinde oluştuğu deyim bloğunun sonunda çalışır duruma gelir.</span><span class="sxs-lookup"><span data-stu-id="f1517-146">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="f1517-147">Bu kuralın iki özel durumu vardır:</span><span class="sxs-lookup"><span data-stu-id="f1517-147">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="f1517-148">Bir döngünün döngü değişkeninin bağlaması, `for` for döngüsünün gövdesinden, ancak döngünün sonundan sonra değil.</span><span class="sxs-lookup"><span data-stu-id="f1517-148">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="f1517-149">Bir döngünün üç bölümü `repeat` / `until` (gövde, test ve düzeltme) tek bir kapsam olarak değerlendirilir, bu nedenle gövdede bağlanan semboller testte ve düzeltmede kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f1517-149">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="f1517-150">Her iki döngü türü için, döngüden geçen her bir geçiş kendi kapsamında yürütülür, bu nedenle önceki bir geçişte bağlamalar daha sonraki bir geçişte kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="f1517-150">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>
<span data-ttu-id="f1517-151">Bu Döngülerde ayrıntılar, [Denetim akışında](xref:microsoft.quantum.guide.controlflow)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="f1517-151">Details on these loops can be found at [Control Flow](xref:microsoft.quantum.guide.controlflow).</span></span>

<span data-ttu-id="f1517-152">Dış bloklarında sembol bağlamaları iç bloklar tarafından devralınır.</span><span class="sxs-lookup"><span data-stu-id="f1517-152">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="f1517-153">Bir sembol, blok başına yalnızca bir kez bağlanabilir; kapsam içindeki başka bir sembolle aynı ada sahip bir sembol tanımlamak geçersizdir ("gölgeleme" yoktur).</span><span class="sxs-lookup"><span data-stu-id="f1517-153">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="f1517-154">Aşağıdaki diziler geçerli olacaktır:</span><span class="sxs-lookup"><span data-stu-id="f1517-154">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="f1517-155">ve</span><span class="sxs-lookup"><span data-stu-id="f1517-155">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

<span data-ttu-id="f1517-156">Ancak bu geçersiz olabilir:</span><span class="sxs-lookup"><span data-stu-id="f1517-156">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="f1517-157">şöyle olacaktır:</span><span class="sxs-lookup"><span data-stu-id="f1517-157">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="whats-next"></a><span data-ttu-id="f1517-158">Sırada Ne Var?</span><span class="sxs-lookup"><span data-stu-id="f1517-158">What's Next?</span></span>
<span data-ttu-id="f1517-159">Q # içinde [qubits Ile çalışma](xref:microsoft.quantum.guide.qubits) hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="f1517-159">Learn about [Working With Qubits](xref:microsoft.quantum.guide.qubits) in Q#.</span></span>