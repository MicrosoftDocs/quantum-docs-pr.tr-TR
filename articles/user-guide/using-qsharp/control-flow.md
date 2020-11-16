---
title: 'İçindeki denetim akışı Q#'
description: Döngüler, koşullar, vb.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: eca37202e5fe9b48dcfdec4eeb4ba6cafaac8723
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691092"
---
# <a name="control-flow-in-no-locq"></a><span data-ttu-id="ca2c2-103">İçindeki denetim akışı Q#</span><span class="sxs-lookup"><span data-stu-id="ca2c2-103">Control flow in Q#</span></span>

<span data-ttu-id="ca2c2-104">Bir işlem veya işlev içinde, her bir ifade, diğer genel zorunlu klasik dillere benzer şekilde sırayla çalışır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-104">Within an operation or function, each statement runs in order, similar to other common imperative classical languages.</span></span>
<span data-ttu-id="ca2c2-105">Ancak, denetim akışını üç farklı şekilde değiştirebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="ca2c2-105">However, you can modify the flow of control in three distinct ways:</span></span>

* <span data-ttu-id="ca2c2-106">`if` deyimler</span><span class="sxs-lookup"><span data-stu-id="ca2c2-106">`if` statements</span></span>
* <span data-ttu-id="ca2c2-107">`for` lerin</span><span class="sxs-lookup"><span data-stu-id="ca2c2-107">`for` loops</span></span>
* <span data-ttu-id="ca2c2-108">`repeat-until-success` lerin</span><span class="sxs-lookup"><span data-stu-id="ca2c2-108">`repeat-until-success` loops</span></span>
* <span data-ttu-id="ca2c2-109">conjugations ( `apply-within` deyimler)</span><span class="sxs-lookup"><span data-stu-id="ca2c2-109">conjugations (`apply-within` statements)</span></span>

<span data-ttu-id="ca2c2-110">`if`Ve `for` Denetim akışı yapıları, çoğu klasik programlama diline tanıdık bir anlamda devam ediyor.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-110">The `if` and `for` control flow constructs proceed in a familiar sense to most classical programming languages.</span></span> <span data-ttu-id="ca2c2-111">[`Repeat-until-success`](#repeat-until-success-loop) döngüler ve [conjugations](#conjugations) Bu makalenin ilerleyen kısımlarında ele alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-111">[`Repeat-until-success`](#repeat-until-success-loop) loops and [conjugations](#conjugations) are discussed later in this article.</span></span>

<span data-ttu-id="ca2c2-112">Daha önemlisi, `for` döngüler ve `if` deyimler, [özelleştirilmiş oluşturmaları](xref:microsoft.quantum.guide.operationsfunctions) otomatik olarak oluşturulan işlemlerde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-112">Importantly, `for` loops and `if` statements can be used in operations for which [specializations](xref:microsoft.quantum.guide.operationsfunctions) are auto-generated.</span></span> <span data-ttu-id="ca2c2-113">Bu senaryoda, bir döngünün adjoint `for` yönü tersine çevirir ve her yinelemenin adjoint değerini alır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-113">In that scenario, the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="ca2c2-114">Bu eylem, "ayakkabılar-ve-SOCKS" ilkesini izler: SOCKS 'yi almayı geri almak istiyorsanız, sonra da sholer ' i ve sonra da</span><span class="sxs-lookup"><span data-stu-id="ca2c2-114">This action follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span> 

## <a name="if-else-if-else"></a><span data-ttu-id="ca2c2-115">If, else-if, Else</span><span class="sxs-lookup"><span data-stu-id="ca2c2-115">If, Else-if, Else</span></span>

<span data-ttu-id="ca2c2-116">`if`İfade, koşullu işlemeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-116">The `if` statement supports conditional processing.</span></span>
<span data-ttu-id="ca2c2-117">Anahtar sözcükten `if` , parantez içindeki bir Boole ifadesiyle ve bir deyim bloğundan ( _then_ bloğu) oluşur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-117">It consists of the keyword `if`, a Boolean expression in parentheses, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="ca2c2-118">İsteğe bağlı olarak, her biri anahtar sözcüğü `elif` , parantez içindeki bir Boole ifadesini ve bir deyim bloğunu ( _Else-If_ bloğu) içeren herhangi bir sayıda Else-If yan tümcesi izleyebilir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-118">Optionally, any number of else-if clauses can follow, each of which consists of the keyword `elif`, a Boolean expression in parentheses, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="ca2c2-119">Son olarak, deyimi isteğe bağlı olarak `else` başka bir ifade bloğunun ( _Else_ bloğu) gelen anahtar sözcükten oluşan bir else yan tümcesi ile bitebileceğiniz anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-119">Finally, the statement can optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>

<span data-ttu-id="ca2c2-120">`if`Koşul değerlendirilir ve *true* ise blok çalıştırılır. *then*</span><span class="sxs-lookup"><span data-stu-id="ca2c2-120">The `if` condition is evaluated, and if it is *true* , the *then* block is run.</span></span>
<span data-ttu-id="ca2c2-121">Koşul *yanlışsa* , ilk else-if koşulu değerlendirilir; Bu doğruysa, *Else-If* bloğu çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-121">If the condition is *false* , then the first else-if condition is evaluated; if that is true, then the *else-if* block is run.</span></span>
<span data-ttu-id="ca2c2-122">Aksi takdirde, ikinci Else-If bloğu değerlendirilir ve ardından, doğru bir koşula sahip bir yan tümce ile karşılaşılana ya da başka bir else-if yan tümcesi bulunmadığından, üçüncü ve bu şekilde devam eder.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-122">Otherwise, the second else-if block evaluates, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="ca2c2-123">*Eğer özgün If* koşulu ve tüm else-if yan tümceleri *yanlış* olarak değerlendirilmişse, varsa *Else* bloğu çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-123">If the original *if* condition and all the else-if clauses evaluate to *false* , the *else* block is run, if provided.</span></span>

<span data-ttu-id="ca2c2-124">Hangi bloğun çalıştığını, kendi kapsamında çalıştığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-124">Note that whichever block runs, it runs within its own scope.</span></span>
<span data-ttu-id="ca2c2-125">Bir, veya bloğunun içinde yapılan bağlamalar, `if` `elif` `else` blok bittikten sonra görünür değildir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-125">Bindings made inside of an `if`, `elif`, or `else` block are not visible after the block ends.</span></span>

<span data-ttu-id="ca2c2-126">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="ca2c2-126">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
<span data-ttu-id="ca2c2-127">veya</span><span class="sxs-lookup"><span data-stu-id="ca2c2-127">or</span></span>
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

## <a name="for-loop"></a><span data-ttu-id="ca2c2-128">for döngüsü</span><span class="sxs-lookup"><span data-stu-id="ca2c2-128">For loop</span></span>

<span data-ttu-id="ca2c2-129">`for`İfade, bir tamsayı aralığı veya dizi üzerinde yinelemeyi destekler.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-129">The `for` statement supports iteration over an integer range or an array.</span></span>
<span data-ttu-id="ca2c2-130">Deyimi, anahtar sözcüğünden `for` , ardından bir sembol veya sembol tanımlama anahtarından, anahtar sözcükten `in` ve Type `Range` ya da Array, All parantez içinde ve bir deyim bloğundan oluşur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-130">The statement consists of the keyword `for`, followed by a symbol or symbol tuple, the keyword `in`, and an expression of type `Range` or array, all in parentheses, and a statement block.</span></span>

<span data-ttu-id="ca2c2-131">İfade bloğu (Döngünün gövdesi), Aralık veya dizideki her bir değere bağlanacak şekilde, tanımlanmış sembol (döngü değişkeni) ile tekrar tekrar çalışır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-131">The statement block (the body of the loop) runs repeatedly, with the defined symbol (the loop variable) bound to each value in the range or array.</span></span>
<span data-ttu-id="ca2c2-132">Aralık ifadesi boş bir aralığa veya diziye değerlendirilirse, gövdenin hiç çalıştırılmadığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-132">Note that if the range expression evaluates to an empty range or array, the body does not run at all.</span></span>
<span data-ttu-id="ca2c2-133">İfade, döngü girilmeden önce tam olarak değerlendirilir ve döngü çalışırken değişmez.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-133">The expression is fully evaluated before entering the loop, and does not change while the loop is running.</span></span>

<span data-ttu-id="ca2c2-134">Döngü değişkeni, döngü gövdesinin her girişinde bağlanır ve gövdenin sonunda ilişkisiz olur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-134">The loop variable is bound at each entrance to the loop body, and is unbound at the end of the body.</span></span>
<span data-ttu-id="ca2c2-135">For döngüsü tamamlandıktan sonra döngü değişkeni bağlanmadı.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-135">The loop variable is not bound after the for loop is completed.</span></span>
<span data-ttu-id="ca2c2-136">Döngü değişkeninin bağlaması sabittir ve diğer değişken bağlamalarıyla aynı kurallara uyar.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-136">The binding of the loop variable is immutable and follows the same rules as other variable bindings.</span></span> 

<span data-ttu-id="ca2c2-137">Bu örneklerde, `qubits` qubits 'in bir yazmacı olur (örneğin, türü `Qubit[]` ),</span><span class="sxs-lookup"><span data-stu-id="ca2c2-137">In these examples, `qubits` is a register of qubits (i.e. of type `Qubit[]`),</span></span> 

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

<span data-ttu-id="ca2c2-138">Sonunda aritmetik-SHIFT-Left ikili işlecini kullandığımızda olduğunu unutmayın `<<<` .</span><span class="sxs-lookup"><span data-stu-id="ca2c2-138">Note that at the end, we utilized the arithmetic-shift-left binary operator, `<<<`.</span></span> <span data-ttu-id="ca2c2-139">Daha fazla bilgi için bkz. [sayısal ifadeler](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span><span class="sxs-lookup"><span data-stu-id="ca2c2-139">For more information, see [Numeric Expressions](xref:microsoft.quantum.guide.expressions#numeric-expressions).</span></span>

## <a name="repeat-until-success-loop"></a><span data-ttu-id="ca2c2-140">Yineleme-Until-başarılı döngüsü</span><span class="sxs-lookup"><span data-stu-id="ca2c2-140">Repeat-until-success loop</span></span>

<span data-ttu-id="ca2c2-141">Q#Dil klasik denetim akışının, qubits 'in ölçüleriyle sonuçlanmasına bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-141">The Q# language allows classical control flow to depend on the results of measuring qubits.</span></span>
<span data-ttu-id="ca2c2-142">Bu özellik, sırasıyla, birimlere uygulama için hesaplama maliyetini azaltabilecekleri güçlü dayalı araçları uygulamaya olanak tanıyor.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-142">This capability, in turn, enables implementing powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span>
<span data-ttu-id="ca2c2-143">Bunun örnekleri, içindeki *yineleme-başarılı* (Rus) desenlerdir Q# .</span><span class="sxs-lookup"><span data-stu-id="ca2c2-143">Examples of this are the *repeat-until-success* (RUS) patterns in Q#.</span></span>
<span data-ttu-id="ca2c2-144">Bu RUS desenleri, temel kapıların bakımından *beklenen* düşük maliyetli dayalı programlarıdır; tahakkuk eden maliyet, gerçek çalıştırmaya ve çoklu olası Branch'in araya yerleştirmesine bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-144">These RUS patterns are probabilistic programs that have an *expected* low cost in terms of elementary gates; the incurred cost depends on the actual run and the interleaving of the multiple possible branchings.</span></span>

<span data-ttu-id="ca2c2-145">Yinele-başarılı (RUS) desenleri kolaylaştırmak için Q# yapıları destekler</span><span class="sxs-lookup"><span data-stu-id="ca2c2-145">To facilitate repeat-until-success (RUS) patterns, Q# supports the constructs</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

<span data-ttu-id="ca2c2-146">`expression`, türünde bir değer değerlendirilen geçerli bir ifadedir `Bool` .</span><span class="sxs-lookup"><span data-stu-id="ca2c2-146">where `expression` is any valid expression that evaluates to a value of type `Bool`.</span></span>
<span data-ttu-id="ca2c2-147">Döngü gövdesi çalışır ve ardından koşul değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-147">The loop body runs, and then the condition is evaluated.</span></span>
<span data-ttu-id="ca2c2-148">Koşul doğru ise, ifade tamamlanır; Aksi takdirde, düzeltme çalışır ve ifade, döngü gövdesiyle başlayarak yeniden çalışır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-148">If the condition is true, then the statement is completed; otherwise, the fixup runs, and the statement runs again, starting with the loop body.</span></span>

<span data-ttu-id="ca2c2-149">Bir RUS döngüsünün üç bölümü (gövde, test ve düzeltme) *her yineleme için* tek bir kapsam olarak değerlendirilir, böylece gövdede bağlanan semboller hem testte hem de düzeltmede kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-149">All three portions of an RUS loop (the body, the test, and the fixup) are treated as a single scope *for each repetition* , so symbols that are bound in the body are available in both the test and the fixup.</span></span>
<span data-ttu-id="ca2c2-150">Ancak, düzeltme çalıştırmasının tamamlanması deyimin kapsamını sonlandırır, böylece gövde veya Düzeltme sırasında yapılan simge bağlamaları sonraki tekrarlarda kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-150">However, completing the run of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="ca2c2-151">Ayrıca, `fixup` ifade genellikle yararlı olur ancak her zaman gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-151">Further, the `fixup` statement is often useful but not always necessary.</span></span>
<span data-ttu-id="ca2c2-152">Gerekli olmadığı durumlarda, yapı</span><span class="sxs-lookup"><span data-stu-id="ca2c2-152">In cases that it is not needed, the construct</span></span>

```qsharp
repeat {
    // do stuff
}
until (expression);
```

<span data-ttu-id="ca2c2-153">aynı zamanda geçerli bir RUS örüntü.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-153">is also a valid RUS pattern.</span></span>

<span data-ttu-id="ca2c2-154">Daha fazla örnek ve ayrıntı için, bu makaledeki [Yinele-Until-Success örneklerine](#repeat-until-success-examples) bakın.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-154">For more examples and details, see [Repeat-until-success examples](#repeat-until-success-examples) in this article.</span></span>

> [!TIP]   
> <span data-ttu-id="ca2c2-155">İşlevler içinde yineleme-başarılı döngüleri kullanmaktan kaçının.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-155">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="ca2c2-156">İşlevler içinde karşılık gelen işlevleri sağlamak için *while* döngüleri kullanın.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-156">Use *while* loops to provide the corresponding functionality inside functions.</span></span> 

## <a name="while-loop"></a><span data-ttu-id="ca2c2-157">while döngüsü</span><span class="sxs-lookup"><span data-stu-id="ca2c2-157">While loop</span></span>

<span data-ttu-id="ca2c2-158">Yinele-Success desenlerinin çok hisse özgü bir connotation vardır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-158">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="ca2c2-159">Bu değerler, ' de adanmış dil yapısı olan belirli hisse algoritmaları sınıflarında yaygın olarak kullanılırlar Q# .</span><span class="sxs-lookup"><span data-stu-id="ca2c2-159">They are widely used in particular classes of quantum algorithms - hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="ca2c2-160">Ancak, bir koşula göre kesintiye uğratır ve bu nedenle derleme zamanında çalışma uzunluğu bilinmiyor döngüsü, bir hisse çalışma zamanında belirli bir durumla işlenir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-160">However, loops that break based on a condition and whose run length is thus unknown at compile-time, are handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="ca2c2-161">Ancak, işlevleri içindeki kullanımları sorunlu değildir çünkü bu döngüler yalnızca geleneksel (hisse olmayan) donanımda çalışan bir kod içerir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-161">However, their use within functions is unproblematic since these loops only contain code that runs on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="ca2c2-162">Q#Bu nedenle, yalnızca işlevler içindeki while döngülerinin kullanımını destekler.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-162">Q#, therefore, supports to use of while loops within functions only.</span></span>
<span data-ttu-id="ca2c2-163">Bir `while` deyim, anahtar sözcükten `while` , parantez içinde Boole ifadesiyle ve deyim bloğundan oluşur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-163">A `while` statement consists of the keyword `while`, a Boolean expression in parentheses, and a statement block.</span></span>
<span data-ttu-id="ca2c2-164">Koşul bloğu (Döngünün gövdesi), koşulun değerlendirildiği sürece çalışır `true` .</span><span class="sxs-lookup"><span data-stu-id="ca2c2-164">The statement block (the body of the loop) runs as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a><span data-ttu-id="ca2c2-165">Conjugations</span><span class="sxs-lookup"><span data-stu-id="ca2c2-165">Conjugations</span></span>

<span data-ttu-id="ca2c2-166">Klasik bitlerin aksine, qubits 'in hala bir daha açık olması durumunda qubits 'in kalan hesaplamada istenmeyen etkileri olabildiğinden, hisse bitlerinin serbest bırakılması biraz daha karmaşıktır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-166">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="ca2c2-167">Belleği serbest bırakmadan önce, bu etkileri doğru "geri alma" sırasında gerçekleştirilen hesaplamaları önlenebilir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-167">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="ca2c2-168">Bu nedenle, hisse kullanımı için genel bir model aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="ca2c2-168">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="ca2c2-169">Q# önceki dönüştürmeyi uygulayan bir Birleşik veren ifadesini destekler.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-169">Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="ca2c2-170">Bu ifadeyi kullanarak, işlem `ApplyWith` aşağıdaki şekilde uygulanabilir:</span><span class="sxs-lookup"><span data-stu-id="ca2c2-170">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="ca2c2-171">Bu tür bir birleşim deyimi, dış ve iç dönüşümler işlem olarak hazır değilse ancak birkaç deyimden oluşan bir blok tarafından daha kolay tanımlanmıyorsa yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-171">Such a conjugation statement becomes useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="ca2c2-172">İçindeki blok içinde tanımlanan deyimler için ters dönüşüm, derleyici tarafından otomatik olarak oluşturulur ve Apply-Block tamamlandıktan sonra çalıştırılır.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-172">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="ca2c2-173">İçindeki blok içinde kullanılan herhangi bir değişebilir değişken, Apply-Block içinde yeniden bağlanamaz, oluşturulan dönüşümün, hesaplamanın içindeki adeklik olduğu garanti edilir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-173">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="return-statement"></a><span data-ttu-id="ca2c2-174">Return Deyimi</span><span class="sxs-lookup"><span data-stu-id="ca2c2-174">Return Statement</span></span>

<span data-ttu-id="ca2c2-175">Return ifadesinde bir işlemin veya işlevin çalışması sona erer ve çağırana bir değer döndürülür.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-175">The return statement ends the run of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="ca2c2-176">Anahtar sözcüğünden `return` , ardından uygun türdeki bir ifadeye ve bir sonlandırma noktalı virgülden oluşur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-176">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="ca2c2-177">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="ca2c2-177">For example,</span></span>
```qsharp
return 1;
```
<span data-ttu-id="ca2c2-178">veya</span><span class="sxs-lookup"><span data-stu-id="ca2c2-178">or</span></span>
```qsharp
return (results, qubits);
```

* <span data-ttu-id="ca2c2-179">Boş bir tanımlama grubu döndüren çağrılabilir, `()` Return ifadesine gerek yoktur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-179">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
* <span data-ttu-id="ca2c2-180">İşlemden veya işlevden erken çıkış belirtmek için öğesini kullanın `return ();` .</span><span class="sxs-lookup"><span data-stu-id="ca2c2-180">To specify an early exit from the operation or function, use `return ();`.</span></span>
<span data-ttu-id="ca2c2-181">Diğer herhangi bir tür döndüren callables, son Return ifadesine gerek duyar.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-181">Callables that return any other type require a final return statement.</span></span>
* <span data-ttu-id="ca2c2-182">Bir işlem içinde en fazla dönüş deyimi sayısı yoktur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-182">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="ca2c2-183">Deyimler bir blok içindeki Return deyimini izif ise derleyici bir uyarı verebilir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-183">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

   
## <a name="fail-statement"></a><span data-ttu-id="ca2c2-184">Fail bildirisi</span><span class="sxs-lookup"><span data-stu-id="ca2c2-184">Fail statement</span></span>

<span data-ttu-id="ca2c2-185">Fail deyimleri bir işlemin çalıştırılmasını sonlandırır ve çağırana bir hata değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-185">The fail statement ends the run of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="ca2c2-186">Anahtar sözcüğünden `fail` ve ardından bir dize ve Sonlandırıcı noktalı virgülden oluşur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-186">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="ca2c2-187">İfade, hata iletisi olarak, dizeyi klasik sürücüye döndürür.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-187">The statement returns the string to the classical driver as the error message.</span></span>

<span data-ttu-id="ca2c2-188">İşlemdeki başarısızlık deyimlerinin sayısı üzerinde hiçbir kısıtlama yoktur.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-188">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="ca2c2-189">Deyimler bir blok içindeki bir fail deyimini izif ise derleyici bir uyarı verebilir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-189">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="ca2c2-190">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="ca2c2-190">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```
<span data-ttu-id="ca2c2-191">ya da, [enterpolasyonlu dizeleri](xref:microsoft.quantum.guide.expressions#interpolated-strings)kullanarak</span><span class="sxs-lookup"><span data-stu-id="ca2c2-191">or, using [interpolated strings](xref:microsoft.quantum.guide.expressions#interpolated-strings),</span></span>
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a><span data-ttu-id="ca2c2-192">Yineleme-Until-Success örnekleri</span><span class="sxs-lookup"><span data-stu-id="ca2c2-192">Repeat-until-success examples</span></span>

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a><span data-ttu-id="ca2c2-193">Irrational Axis hakkında tek qubit döndürme için RUS stili</span><span class="sxs-lookup"><span data-stu-id="ca2c2-193">RUS pattern for single-qubit rotation about an irrational axis</span></span> 

<span data-ttu-id="ca2c2-194">Tipik bir kullanım durumunda aşağıdaki Q# işlem, {5} Bloch Sphere üzerinde $ (I + 2ı Z)/\sqrt $ bir ırrational ekseninin etrafında bir döndürme uygular.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-194">In a typical use case, the following Q# operation implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="ca2c2-195">Uygulama, bilinen bir RUS modelini kullanır:</span><span class="sxs-lookup"><span data-stu-id="ca2c2-195">The implementation uses a known RUS pattern:</span></span>

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a><span data-ttu-id="ca2c2-196">Kapsam içinde kesilebilir değişkenle birlikte RUS döngüsü</span><span class="sxs-lookup"><span data-stu-id="ca2c2-196">RUS loop with a mutable variable in scope</span></span>

<span data-ttu-id="ca2c2-197">Bu örnek, `finished` Tüm tekrarlama-Until-düzeltme döngüsünün kapsamı içinde olan ve düzeltme adımında güncelleştirildikten sonra başlatılan, kesilebilir değişken kullanımını gösterir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-197">This example shows the use of a mutable variable, `finished`, which is within the scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

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

### <a name="rus-without-fixup"></a><span data-ttu-id="ca2c2-198">Şu olmadan RUS `fixup`</span><span class="sxs-lookup"><span data-stu-id="ca2c2-198">RUS without `fixup`</span></span>

<span data-ttu-id="ca2c2-199">Bu örnekte, düzeltme adımı olmadan bir RUS döngüsü gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-199">This example shows an RUS loop without the fixup step.</span></span> <span data-ttu-id="ca2c2-200">Kod, {5} ve kapılarını kullanarak önemli bir döndürme kapısı uygulayan $V _3 = (\cıvalation+ 2 ı Z)/\sqrt $ olan bir dayalı devresi `H` `T` .</span><span class="sxs-lookup"><span data-stu-id="ca2c2-200">The code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the `H` and `T` gates.</span></span>
<span data-ttu-id="ca2c2-201">Döngü, ortalama $ \frac $ tekrarları içinde sona erer {8} {5} .</span><span class="sxs-lookup"><span data-stu-id="ca2c2-201">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="ca2c2-202">Daha fazla ayrıntı için bkz. [*yineleme-Until-başarılı: tek qubit unityalarının belirleyici olmayan ayrıştırma*](https://arxiv.org/abs/1311.1074) (paetznick ve svore, 2014).</span><span class="sxs-lookup"><span data-stu-id="ca2c2-202">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for more details.</span></span>

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

### <a name="rus-to-prepare-a-quantum-state"></a><span data-ttu-id="ca2c2-203">Ru bir hisse durumu hazırlamak için</span><span class="sxs-lookup"><span data-stu-id="ca2c2-203">RUS to prepare a quantum state</span></span>

<span data-ttu-id="ca2c2-204">Son olarak, {1} {3} {2} {0} $ \ket{+} $ durumundan başlayarak bir hisse durumu $ \frac {\sqrt} \left (\sqrt \ Tus+ {1} \tus\right) $ hazırlamak için bir Rus deseninin örneği aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-204">Finally, here is an example of an RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span>

<span data-ttu-id="ca2c2-205">Bu işlemde gösterilen Notable programlama özellikleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="ca2c2-205">Notable programmatic features shown in this operation are:</span></span>

* <span data-ttu-id="ca2c2-206">Döngünün daha karmaşık bir `fixup` parçası olan ve bu da hisse işlemleri içerir.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-206">A more complex `fixup` part of the loop, which involves quantum operations.</span></span> 
* <span data-ttu-id="ca2c2-207">`AssertMeasurementProbability`Programın belirtilen belirli noktalarda hisse miktarını ölçme olasılığını belirlemek için deyimlerin kullanılması.</span><span class="sxs-lookup"><span data-stu-id="ca2c2-207">The use of `AssertMeasurementProbability` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span>

<span data-ttu-id="ca2c2-208">Ve işlemleri hakkında daha fazla bilgi için [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) bkz. [test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging).</span><span class="sxs-lookup"><span data-stu-id="ca2c2-208">For more information about the [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) and [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) operations, see [Testing and debugging](xref:microsoft.quantum.guide.testingdebugging).</span></span>

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
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

<span data-ttu-id="ca2c2-209">Daha fazla bilgi için bkz. [Standart kitaplıkla birlikte sunulan birim testi örneği](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span><span class="sxs-lookup"><span data-stu-id="ca2c2-209">For more information, see [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca2c2-210">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="ca2c2-210">Next steps</span></span>

<span data-ttu-id="ca2c2-211">' De [test ve hata ayıklama](xref:microsoft.quantum.guide.testingdebugging) hakkında bilgi edinin Q# .</span><span class="sxs-lookup"><span data-stu-id="ca2c2-211">Learn about [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging) in Q#.</span></span>
