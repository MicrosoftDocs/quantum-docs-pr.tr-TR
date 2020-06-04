---
title: 'Q içindeki denetim akışı #'
description: Döngüler, koşullar, vb.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326549"
---
# <a name="control-flow-in-q"></a><span data-ttu-id="346a3-103">Q içindeki denetim akışı #</span><span class="sxs-lookup"><span data-stu-id="346a3-103">Control Flow in Q#</span></span>

<span data-ttu-id="346a3-104">Bir işlem veya işlev içinde her bir ifade, en sık kullanılan zorunlu klasik dillere benzer şekilde sırayla yürütülür.</span><span class="sxs-lookup"><span data-stu-id="346a3-104">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="346a3-105">Bu denetim akışı, ancak üç farklı şekilde değiştirilebilir:</span><span class="sxs-lookup"><span data-stu-id="346a3-105">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="346a3-106">`if`deyimler</span><span class="sxs-lookup"><span data-stu-id="346a3-106">`if` statements</span></span>
- <span data-ttu-id="346a3-107">`for`lerin</span><span class="sxs-lookup"><span data-stu-id="346a3-107">`for` loops</span></span>
- <span data-ttu-id="346a3-108">`repeat`-`until`lerin</span><span class="sxs-lookup"><span data-stu-id="346a3-108">`repeat`-`until` loops</span></span>

<span data-ttu-id="346a3-109">Son tartışmayı [aşağıda](#repeat-until-success-loop)daha ileri erteliyoruz.</span><span class="sxs-lookup"><span data-stu-id="346a3-109">We defer discussion of the latter to further [below](#repeat-until-success-loop).</span></span>
<span data-ttu-id="346a3-110">`if` `for` Ancak denetim akışı yapıları, klasik programlama dillerinin çoğu için tanıdık bir anlata devam ediyor.</span><span class="sxs-lookup"><span data-stu-id="346a3-110">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>

<span data-ttu-id="346a3-111">Daha önemlisi, `for` döngüler ve `if` deyimler, özelleştirilmiş oluşturmaları otomatik olarak oluşturulan işlemlerde bile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="346a3-111">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="346a3-112">Bu durumda, bir döngünün adjoint `for` yönü tersine çevirir ve her yinelemenin adeklerini alır.</span><span class="sxs-lookup"><span data-stu-id="346a3-112">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="346a3-113">Bu, "ayakkabılar-ve-SOCKS" ilkesini izler: Socks ' yi almayı geri almak istiyorsanız, ve ardından</span><span class="sxs-lookup"><span data-stu-id="346a3-113">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="346a3-114">Bu işlem, siz de daha az bir işlem yapmaya çalışır.</span><span class="sxs-lookup"><span data-stu-id="346a3-114">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="if-else-if-else"></a><span data-ttu-id="346a3-115">If, else-if, Else</span><span class="sxs-lookup"><span data-stu-id="346a3-115">If, Else-if, Else</span></span>

<span data-ttu-id="346a3-116">`if`İfade koşullu yürütmeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="346a3-116">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="346a3-117">Anahtar sözcüğü `if` , açık parantez `(` , Boole ifadesi, kapatma parantezi `)` ve deyim bloğu ( _then_ bloğu) oluşur.</span><span class="sxs-lookup"><span data-stu-id="346a3-117">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="346a3-118">Bu, her biri anahtar sözcüğü `elif` , bir açık parantez `(` , Boole ifadesi, kapatma parantezi `)` ve deyim bloğu ( _Else-If_ bloğu) içeren herhangi bir sayıda Else-If yan tümcesi tarafından izlenebilir.</span><span class="sxs-lookup"><span data-stu-id="346a3-118">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="346a3-119">Son olarak, deyimi isteğe bağlı olarak `else` başka bir ifade bloğunun ( _Else_ bloğu) gelen anahtar sözcükten oluşan bir else yan tümcesi ile bitebileceğiniz anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="346a3-119">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="346a3-120">`if`Koşul değerlendirilir ve true ise blok yürütülür.</span><span class="sxs-lookup"><span data-stu-id="346a3-120">The `if` condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="346a3-121">Koşul yanlışsa, ilk else-if koşulu değerlendirilir; true ise, Else-If bloğu yürütülür.</span><span class="sxs-lookup"><span data-stu-id="346a3-121">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="346a3-122">Aksi takdirde, ikinci Else-If bloğu test edilir ve ardından üçüncü, vb. doğru bir koşula sahip bir yan tümce ile karşılaşılana ya da başka bir else-if yan tümcesi içermeyecek şekilde devam eder.</span><span class="sxs-lookup"><span data-stu-id="346a3-122">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="346a3-123">Özgün If koşulu ve tüm else-if yan tümceleri yanlış olarak değerlendirilmişse, varsa Else bloğu yürütülür.</span><span class="sxs-lookup"><span data-stu-id="346a3-123">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="346a3-124">Hangi bloğun yürütüldüğü, kendi kapsamında yürütüleceğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="346a3-124">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="346a3-125">Bir `if` , veya bloğunun içinde yapılan bağlamalar, `elif` `else` sonunda görünür değildir.</span><span class="sxs-lookup"><span data-stu-id="346a3-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after its end.</span></span>

<span data-ttu-id="346a3-126">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="346a3-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="346a3-127">veya</span><span class="sxs-lookup"><span data-stu-id="346a3-127">or</span></span>
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a><span data-ttu-id="346a3-128">For döngüsü</span><span class="sxs-lookup"><span data-stu-id="346a3-128">For Loop</span></span>

<span data-ttu-id="346a3-129">İfade, bir `for` tamsayı aralığı veya dizi üzerinde yinelemeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="346a3-129">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="346a3-130">Deyimi, anahtar sözcüğünden, bir `for` Açık parantezden `(` , ardından bir sembol veya sembol tanımlama anahtarından, anahtar sözcükten `in` , bir tür veya diziye, bir `Range` kapatma parantezine `)` ve bir deyim bloğuna sahip.</span><span class="sxs-lookup"><span data-stu-id="346a3-130">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="346a3-131">İfade bloğu (Döngünün gövdesi), her bir değere veya dizideki her bir değere bağlantılı tanımlanmış simgeler (döngü değişkenleri) ile tekrar tekrar yürütülür.</span><span class="sxs-lookup"><span data-stu-id="346a3-131">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="346a3-132">Aralık ifadesi boş bir aralığa veya diziye değerlendirilirse, gövdenin hiç yürütülmeyeceğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="346a3-132">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="346a3-133">İfade, döngü girilmeden önce tam olarak değerlendirilir ve döngü yürütülürken değişmeyecektir.</span><span class="sxs-lookup"><span data-stu-id="346a3-133">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="346a3-134">Döngü değişkeni, her giriş gövdesine bağlanır ve gövdenin sonunda ilişkisiz olur.</span><span class="sxs-lookup"><span data-stu-id="346a3-134">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="346a3-135">Özellikle, for döngüsü tamamlandıktan sonra döngü değişkeni bağlantılı değildir.</span><span class="sxs-lookup"><span data-stu-id="346a3-135">In particular, the loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="346a3-136">Belirtilen sembol (ler) in bağlaması sabittir ve diğer değişken bağlamalarıyla aynı kurallara uyar.</span><span class="sxs-lookup"><span data-stu-id="346a3-136">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="346a3-137">Bazı örnekler için, `qubits` qubits 'in bir yazmacı olur (örneğin `Qubit[]` , türü),</span><span class="sxs-lookup"><span data-stu-id="346a3-137">For some examples, supposing `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```
<span data-ttu-id="346a3-138">Sonunda, ' nin aritmetik ve sol ikili işlecini kullandığımızda, `<<<` ayrıntıları [sayısal ifadelerde](xref:microsoft.quantum.guide.expressions#numeric-expressions) nerede olabileceğini unutmayın</span><span class="sxs-lookup"><span data-stu-id="346a3-138">Note that at the end we utilized the arithmetic-shift-left binary operator, `<<<`, details of which can be found at [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions)</span></span>


## <a name="repeat-until-success-loop"></a><span data-ttu-id="346a3-139">Yineleme-Until-başarılı döngüsü</span><span class="sxs-lookup"><span data-stu-id="346a3-139">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="346a3-140">Q # dili, mebitleri ölçmeye yönelik sonuçlara bağlı olarak klasik denetim akışına izin verir.</span><span class="sxs-lookup"><span data-stu-id="346a3-140">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="346a3-141">Bu özellik sırasıyla, birimlere uygulama için hesaplama maliyetini azaltabilecekleri güçlü dayalı araçları uygulamaya olanak tanıyor.</span><span class="sxs-lookup"><span data-stu-id="346a3-141">This capability in turn enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="346a3-142">Örnek olarak, Q # içinde *Yinele-başarılı* (ru) desenleri uygulamak çok kolaydır.</span><span class="sxs-lookup"><span data-stu-id="346a3-142">As an example, it is easy to implement so-called *Repeat-Until-Success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="346a3-143">Bu RUS desenleri, temel kapıların bakımından *beklenen* düşük maliyetli dayalı programlarıdır, ancak gerçek maliyetten gerçek bir çalıştırmaya ve çeşitli olası branchlerin gerçek bir aramasına bağlı olarak değişir.</span><span class="sxs-lookup"><span data-stu-id="346a3-143">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span>

<span data-ttu-id="346a3-144">Yinele-başarılı (RUS) desenleri kolaylaştırmak için, Q # yapıları destekler</span><span class="sxs-lookup"><span data-stu-id="346a3-144">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="346a3-145">`expression`, türünde bir değer değerlendirilen geçerli bir ifadedir `Bool` .</span><span class="sxs-lookup"><span data-stu-id="346a3-145">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="346a3-146">Döngü gövdesi yürütülür ve ardından koşul değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="346a3-146">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="346a3-147">Koşul doğru ise, ifade tamamlanır; Aksi takdirde, düzeltme yürütülür ve ifade, döngü gövdesiyle başlayarak yeniden yürütülür.</span><span class="sxs-lookup"><span data-stu-id="346a3-147">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>

<span data-ttu-id="346a3-148">Yineleme/Until döngüsünün (gövde, test ve düzeltme) üç bölümü *her yineleme için*tek bir kapsam olarak değerlendirilir, bu nedenle gövdede bağlanan semboller testte ve düzeltmede kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="346a3-148">All three portions of a repeat/until loop (the body, the test, and the fixup) are treated as a single scope *for each repetition*, so symbols that are bound in the body are available in the test and in the fixup.</span></span>
<span data-ttu-id="346a3-149">Ancak, düzeltme yürütme işlemini tamamlamak deyimin kapsamını sonlandırır, böylece gövde veya Düzeltme sırasında yapılan simge bağlamaları sonraki tekrarlarda kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="346a3-149">However completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="346a3-150">Ayrıca, `fixup` ifade genellikle yararlı olur ancak her zaman gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="346a3-150">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="346a3-151">Gerekli olmadığı durumlarda, yapı</span><span class="sxs-lookup"><span data-stu-id="346a3-151">In cases that it is not needed, the construct</span></span>
```qsharp
repeat {
    // do stuff
}
until (expression);
```
<span data-ttu-id="346a3-152">aynı zamanda geçerli bir RUS örüntü.</span><span class="sxs-lookup"><span data-stu-id="346a3-152">is also a valid RUS pattern.</span></span>

<span data-ttu-id="346a3-153">Bu sayfanın en altında, [Rus döngülerinin bazı örneklerini](#repeat-until-success-examples)sunuyoruz.</span><span class="sxs-lookup"><span data-stu-id="346a3-153">At the bottom of this page we present some [examples of RUS loops](#repeat-until-success-examples).</span></span>

> [!TIP]   
> <span data-ttu-id="346a3-154">İşlevler içinde yineleme-başarılı döngüleri kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="346a3-154">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="346a3-155">Karşılık gelen işlevler, işlevlerde döngüler sırasında sağlanır.</span><span class="sxs-lookup"><span data-stu-id="346a3-155">The corresponding functionality is provided by while loops in functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="346a3-156">While döngüsü</span><span class="sxs-lookup"><span data-stu-id="346a3-156">While Loop</span></span>

<span data-ttu-id="346a3-157">Yinele-Success desenlerinin çok hisse özgü bir connotation vardır.</span><span class="sxs-lookup"><span data-stu-id="346a3-157">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="346a3-158">Bu diller, belirli hisse algoritmaları sınıflarında yaygın olarak kullanılır. bu nedenle, Q # içinde adanmış dil yapısı.</span><span class="sxs-lookup"><span data-stu-id="346a3-158">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="346a3-159">Ancak, bir koşula göre kesintiye uğratır ve bu nedenle derleme sırasında yürütme uzunluğunun bilinmediği, bir hisse çalışma zamanında belirli bir ele alınabilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="346a3-159">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="346a3-160">Diğer yandan işlevleri içindeki kullanımları sorunlu değildir, çünkü bunlar yalnızca geleneksel (hisse olmayan) donanımda yürütülecek kodu içerir.</span><span class="sxs-lookup"><span data-stu-id="346a3-160">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="346a3-161">Q # bu nedenle, yalnızca işlevler içindeki while döngülerinin kullanımını destekler.</span><span class="sxs-lookup"><span data-stu-id="346a3-161">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="346a3-162">Deyim, bir `while` `while` açık parantez `(` , bir koşul (yani Boolean ifadesi), bir kapatma parantezi `)` ve deyim bloğu oluşur.</span><span class="sxs-lookup"><span data-stu-id="346a3-162">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="346a3-163">İfade bloğu (Döngünün gövdesi), koşulun değerlendirildiği sürece yürütülür `true` .</span><span class="sxs-lookup"><span data-stu-id="346a3-163">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a><span data-ttu-id="346a3-164">Return Deyimi</span><span class="sxs-lookup"><span data-stu-id="346a3-164">Return Statement</span></span>

<span data-ttu-id="346a3-165">Return deyimleri bir işlemin veya işlevin yürütmesini sonlandırır ve çağırana bir değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="346a3-165">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="346a3-166">Anahtar sözcüğünden `return` , ardından uygun türdeki bir ifadeye ve bir sonlandırma noktalı virgülden oluşur.</span><span class="sxs-lookup"><span data-stu-id="346a3-166">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="346a3-167">Boş bir tanımlama grubu döndüren çağrılabilir, `()` Return ifadesine gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="346a3-167">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="346a3-168">Erken çıkış istenirse `return ()` Bu durumda kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="346a3-168">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="346a3-169">Diğer herhangi bir tür döndüren callables, son Return ifadesine gerek duyar.</span><span class="sxs-lookup"><span data-stu-id="346a3-169">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="346a3-170">Bir işlem içinde en fazla dönüş deyimi sayısı yoktur.</span><span class="sxs-lookup"><span data-stu-id="346a3-170">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="346a3-171">Deyimler bir blok içindeki Return deyimini izif ise derleyici bir uyarı verebilir.</span><span class="sxs-lookup"><span data-stu-id="346a3-171">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="346a3-172">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="346a3-172">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="346a3-173">veya</span><span class="sxs-lookup"><span data-stu-id="346a3-173">or</span></span>
```qsharp
return ();
```
<span data-ttu-id="346a3-174">veya</span><span class="sxs-lookup"><span data-stu-id="346a3-174">or</span></span>
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a><span data-ttu-id="346a3-175">Fail bildirisi</span><span class="sxs-lookup"><span data-stu-id="346a3-175">Fail Statement</span></span>

<span data-ttu-id="346a3-176">Fail deyimleri bir işlemin yürütülmesini sonlandırır ve çağırana bir hata değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="346a3-176">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="346a3-177">Anahtar sözcüğünden `fail` ve ardından bir dize ve Sonlandırıcı noktalı virgülden oluşur.</span><span class="sxs-lookup"><span data-stu-id="346a3-177">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="346a3-178">Dize, hata iletisi olarak klasik sürücüye döndürülür.</span><span class="sxs-lookup"><span data-stu-id="346a3-178">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="346a3-179">İşlemdeki başarısızlık deyimlerinin sayısı üzerinde hiçbir kısıtlama yoktur.</span><span class="sxs-lookup"><span data-stu-id="346a3-179">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="346a3-180">Deyimler bir blok içindeki bir fail deyimini izif ise derleyici bir uyarı verebilir.</span><span class="sxs-lookup"><span data-stu-id="346a3-180">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="346a3-181">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="346a3-181">For example,</span></span>
```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="346a3-182">ya da, [enterpolasyonlu dizeleri](xref:microsoft.quantum.guide.expressions#interpolated-strings)kullanarak</span><span class="sxs-lookup"><span data-stu-id="346a3-182">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="346a3-183">Yineleme-Until-Success örnekleri</span><span class="sxs-lookup"><span data-stu-id="346a3-183">Repeat-Until-Success Examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="346a3-184">Irrational Axis hakkında tek qubit döndürme için RUS stili</span><span class="sxs-lookup"><span data-stu-id="346a3-184">RUS pattern for single qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="346a3-185">Tipik bir kullanım durumunda, aşağıdaki Q # işlemi Bloch Sphere üzerinde $ (I + 2i Z)/\sqrt $ bir ırrational Axis etrafında bir döndürme uygular {5} .</span><span class="sxs-lookup"><span data-stu-id="346a3-185">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="346a3-186">Bu, bilinen bir RUS kalıbı kullanılarak gerçekleştirilir:</span><span class="sxs-lookup"><span data-stu-id="346a3-186">This is accomplished by using a known RUS pattern:</span></span>

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-mutable-variable-in-scope"></a><span data-ttu-id="346a3-187">Kapsam içinde kesilebilir değişkenle birlikte RUS döngüsü</span><span class="sxs-lookup"><span data-stu-id="346a3-187">RUS loop with mutable variable in scope</span></span>

<span data-ttu-id="346a3-188">Bu örnek, `finished` tüm yineleme-sonu-düzeltme döngüsü kapsamında olan ve düzeltme adımında kullanılmadan önce başlatılan bir kesilebilir değişkeninin kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="346a3-188">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a><span data-ttu-id="346a3-189">Şu olmadan RUS`fixup`</span><span class="sxs-lookup"><span data-stu-id="346a3-189">RUS without `fixup`</span></span>

<span data-ttu-id="346a3-190">Örneğin, aşağıdaki kod, ve kapılarını kullanarak önemli bir döndürme kapısı uygulayan bir dayalı devresi $V _3 = (\cıvalation+ 2 ı Z)/\sqrt {5} $ `H` `T` .</span><span class="sxs-lookup"><span data-stu-id="346a3-190">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="346a3-191">Döngü, ortalama $ \frac $ tekrarları içinde sona erer {8} {5} .</span><span class="sxs-lookup"><span data-stu-id="346a3-191">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="346a3-192">Daha fazla ayrıntı için bkz. [*yineleme-Until-başarılı: tek qubit unityalarının belirleyici olmayan ayrıştırma*](https://arxiv.org/abs/1311.1074) (paetznick ve svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="346a3-192">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="346a3-193">Ru bir hisse durumu hazırlamak için</span><span class="sxs-lookup"><span data-stu-id="346a3-193">RUS to prepare a quantum state</span></span>

<span data-ttu-id="346a3-194">Son olarak, {1} {3} {2} {0} $ \ket{+} $ durumundan başlayarak bir hisse durumu $ \frac {\sqrt} \left (\sqrt \ Tus+ {1} \tus\right) $ hazırlamak için bir Rus deseninin örneğini gösteririz.</span><span class="sxs-lookup"><span data-stu-id="346a3-194">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>
<span data-ttu-id="346a3-195">Ayrıca bkz. [Standart kitaplıkla birlikte sunulan birim testi örneği](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="346a3-195">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

<span data-ttu-id="346a3-196">Bu işlemde gösterilen önemli programlı özellikler, bu döngünün daha karmaşık bir `fixup` parçasıdır ve bu da, hisse ve `AssertProb` programdaki belirli noktalarda hisse durumu ölçme olasılığını belirlemek için deyimleri kullanır.</span><span class="sxs-lookup"><span data-stu-id="346a3-196">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop, which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>
<span data-ttu-id="346a3-197">Ve işlemleri hakkında daha fazla bilgi için bkz. [test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) .</span><span class="sxs-lookup"><span data-stu-id="346a3-197">See also [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging) for more information about the [`Assert`](xref:microsoft.quantum.intrinsic.assert) and [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operations.</span></span>


## <a name="next-steps"></a><span data-ttu-id="346a3-198">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="346a3-198">Next steps</span></span>

<span data-ttu-id="346a3-199">Soru-cevap [Ile test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging) hakkında bilgi edinin.</span><span class="sxs-lookup"><span data-stu-id="346a3-199">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>