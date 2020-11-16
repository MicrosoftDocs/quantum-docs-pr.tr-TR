---
title: 'İçindeki türler Q#'
description: 'Programlama dilinde kullanılan farklı türler hakkında bilgi edinin Q# .'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 349138984387cc564cca18ea09c7bf161524b0b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691613"
---
# <a name="types-in-no-locq"></a><span data-ttu-id="a4113-103">İçindeki türler Q#</span><span class="sxs-lookup"><span data-stu-id="a4113-103">Types in Q#</span></span>

<span data-ttu-id="a4113-104">Bu makalede Q# tür modeli ve türleri belirtmek ve bunlarla çalışmak için sözdizimi açıklanır.</span><span class="sxs-lookup"><span data-stu-id="a4113-104">This article describes the Q# type model and the syntax for specifying and working with types.</span></span> <span data-ttu-id="a4113-105">Bu türlerin ifadelerinde oluşturma ve üzerinde işlem yapma hakkında ayrıntılı bilgi için bkz. [tür ifadeleri](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="a4113-105">For details on how to create and operate on expressions of these types, see [Type Expressions](xref:microsoft.quantum.guide.expressions).</span></span>

<span data-ttu-id="a4113-106">Q#Bu tür dikkatle kullanılması derleyicinin derleme zamanında programlar hakkında güçlü garantiler sağlamasına yardımcı olabileceğini belirten, *kesin olarak belirlenmiş* bir dil olduğunu unutmayın Q# .</span><span class="sxs-lookup"><span data-stu-id="a4113-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="a4113-107">Mümkün olan en güçlü garantiyi sağlamak için, içindeki türler arasındaki dönüştürmeler, Q# bu dönüştürmeyi ifade eden işlevlere yapılan çağrılar kullanılarak açık olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a4113-107">To provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> 
<span data-ttu-id="a4113-108">Q# ad alanının bir parçası olarak çeşitli işlevler sağlar <xref:Microsoft.Quantum.Convert> .</span><span class="sxs-lookup"><span data-stu-id="a4113-108">Q# provides a variety of such functions as a part of the <xref:Microsoft.Quantum.Convert> namespace.</span></span>
<span data-ttu-id="a4113-109">Diğer yandan, uyumlu türlere yönelik olarak yapılan yayınlar örtülü olarak gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="a4113-109">Upcasts to compatible types, on the other hand, happen implicitly.</span></span> 

<span data-ttu-id="a4113-110">Q# , doğrudan kullanılan ilkel türler ve diğer türlerden yeni türler oluşturmak için çeşitli yollar sağlar.</span><span class="sxs-lookup"><span data-stu-id="a4113-110">Q# provides both primitive types, which are used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="a4113-111">Bu makalenin geri kalanında anlatılmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a4113-111">We describe each in the rest of this article.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="a4113-112">İlkel Türler</span><span class="sxs-lookup"><span data-stu-id="a4113-112">Primitive Types</span></span>

<span data-ttu-id="a4113-113">Q#Dil, hepsi doğrudan programlarda kullanabileceğiniz aşağıdaki *temel türleri* sağlar Q# .</span><span class="sxs-lookup"><span data-stu-id="a4113-113">The Q# language provides the following *primitive types* , all of which you can use directly in Q# programs.</span></span> <span data-ttu-id="a4113-114">Bu temel türleri yeni türler oluşturmak için de kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4113-114">You can also use these primitive types to construct new types.</span></span>

- <span data-ttu-id="a4113-115">`Int`Tür, 64 bitlik işaretli bir tamsayıyı temsil eder, örneğin,, `2` , `107` `-5` .</span><span class="sxs-lookup"><span data-stu-id="a4113-115">The `Int` type represents a 64-bit signed integer, for example, `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="a4113-116">`BigInt`Türü, rastgele boyutun işaretli bir tamsayı temsil eder, örneğin,, `2L` , `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="a4113-116">The `BigInt` type represents a signed integer of arbitrary size, for example, `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="a4113-117">Bu tür .NET tabanlıdır <xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="a4113-117">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="a4113-118">türüyle.</span><span class="sxs-lookup"><span data-stu-id="a4113-118">type.</span></span>

- <span data-ttu-id="a4113-119">`Double`Tür, bir çift duyarlıklı kayan noktalı sayıyı temsil eder, örneğin,,, `0.0` `-1.3` `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="a4113-119">The `Double` type represents a double-precision floating-point number, for example, `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="a4113-120">`Bool`Tür ya da bir Boolean değerini temsil eder `true` `false` .</span><span class="sxs-lookup"><span data-stu-id="a4113-120">The `Bool` type represents a Boolean value of either `true` or `false`.</span></span>
- <span data-ttu-id="a4113-121">`Range`Türü, tarafından belirtilen, `start..step..stop` adımın isteğe bağlı olduğunu gösteren bir tamsayılar dizisini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a4113-121">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="a4113-122">Örneğin, `start .. stop` öğesine karşılık gelir `start..1..stop` ve `1..2..7` $ \{ 1, 3, 5, 7 $ dizisini temsil eder \} .</span><span class="sxs-lookup"><span data-stu-id="a4113-122">For example, `start .. stop` corresponds to `start..1..stop`, and `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="a4113-123">`String`Tür, bir kez oluşturulduktan sonra kullanıcıya donuk olan Unicode karakterlerinden oluşan bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="a4113-123">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="a4113-124">`string`Bir hata veya tanılama olayı durumunda iletileri klasik bir konağa raporlamak için türünü kullanın.</span><span class="sxs-lookup"><span data-stu-id="a4113-124">Use the `string` type to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="a4113-125">`Unit`Tür yalnızca bir değere sahip olabilir `()` .</span><span class="sxs-lookup"><span data-stu-id="a4113-125">The `Unit` type can have only one value, `()`.</span></span> 
  <span data-ttu-id="a4113-126">Bir Q# işlev veya işlemin hiçbir bilgi döndürdüğünü belirtmek için bu türü kullanın.</span><span class="sxs-lookup"><span data-stu-id="a4113-126">Use this type to indicate that a Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="a4113-127">`Qubit`Tür bir hisse bitini veya qubit 'i temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a4113-127">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="a4113-128">`Qubit`, kullanıcının opaktır.</span><span class="sxs-lookup"><span data-stu-id="a4113-128">`Qubit`s are opaque to the user.</span></span> <span data-ttu-id="a4113-129">Bunlar ile mümkün olan tek işlem, başka bir işleme geçirilmekten farklı kimlik (eşitlik) için test amaçlıdır.</span><span class="sxs-lookup"><span data-stu-id="a4113-129">The only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="a4113-130">Sonuç olarak, `Qubit` bir hisse işlemcisi (veya hisse Benzetici simülatörü) üzerinde iç yönergeleri çağırarak öğeleri ' de uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4113-130">Ultimately, you implement actions on `Qubit`s by calling intrinsic instructions on a quantum processor (or a quantum simulator).</span></span>
- <span data-ttu-id="a4113-131">`Pauli`Tür, dört adet tek qubit Pauli işleçlerinden birini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a4113-131">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="a4113-132">Bu türü, döndürmeler için temel işlemi göstermek ve ölçülecek observable 'ı belirtmek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="a4113-132">Use this type to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="a4113-133">Dört olası değeri olan numaralandırılmış bir türdür: `PauliI` ,, `PauliX` `PauliY` , ve `PauliZ` , türünde sabitler `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="a4113-133">It is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="a4113-134">`Result`Tür, ölçümün sonucunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a4113-134">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="a4113-135">Bu, iki olası değeri olan `One` ve türünde sabitler olan numaralandırılmış bir türdür `Zero` `Result` .</span><span class="sxs-lookup"><span data-stu-id="a4113-135">It is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="a4113-136">`Zero` + 1 eigenvalue değerinin ölçüldüğünü belirtir; `One` -1 eigenvalue değerinin ölçüldüğünü gösterir.</span><span class="sxs-lookup"><span data-stu-id="a4113-136">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue was measured.</span></span>

<span data-ttu-id="a4113-137">,,,,,, `true` `false` Ve sabitleri `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` içindeki tüm ayrılmış semboller Q# .</span><span class="sxs-lookup"><span data-stu-id="a4113-137">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="a4113-138">Dizi türleri</span><span class="sxs-lookup"><span data-stu-id="a4113-138">Array Types</span></span>

* <span data-ttu-id="a4113-139">Geçerli herhangi bir Q# tür için, bu türdeki bir değer dizisini temsil eden bir tür vardır.</span><span class="sxs-lookup"><span data-stu-id="a4113-139">For any valid Q# type, there is a type that represents an array of values of that type.</span></span>
    <span data-ttu-id="a4113-140">Örneğin, `Qubit[]` ve `(Bool, Pauli)[]` `Qubit` değerlerin dizilerini ve `(Bool, Pauli)` demet değerlerini temsil edin.</span><span class="sxs-lookup"><span data-stu-id="a4113-140">For example, `Qubit[]` and `(Bool, Pauli)[]` represent arrays of `Qubit` values and `(Bool, Pauli)` tuple values.</span></span>

* <span data-ttu-id="a4113-141">Dizi dizisi de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="a4113-141">An array of arrays is also valid.</span></span> <span data-ttu-id="a4113-142">Önceki örnekte genişletilen dizi dizisi `(Bool, Pauli)` gösterilir `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="a4113-142">Expanding on the previous example, an array of `(Bool, Pauli)` arrays is denoted `(Bool, Pauli)[][]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="a4113-143">Bu örnek, `(Bool, Pauli)[][]` dikdörtgen bir iki boyutlu diziyi değil, potansiyel olarak pürüzlü dizi dizileri temsil eder.</span><span class="sxs-lookup"><span data-stu-id="a4113-143">This example, `(Bool, Pauli)[][]`, represents a potentially jagged array of arrays and not a rectangular two-dimensional array.</span></span> <span data-ttu-id="a4113-144">Q# dikdörtgen çok boyutlu dizileri desteklemez.</span><span class="sxs-lookup"><span data-stu-id="a4113-144">Q# does not support rectangular multi-dimensional arrays.</span></span>

* <span data-ttu-id="a4113-145">Bir dizi değeri Q# , içinde olduğu gibi bir dizinin öğeleri etrafında köşeli parantezler kullanılarak kaynak kodunda yazılabilir `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="a4113-145">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="a4113-146">Dizideki tüm öğelerin ortak temel türü bir dizi sabit değerinin türünü belirler.</span><span class="sxs-lookup"><span data-stu-id="a4113-146">The common base type of all items in the array determines the type of an array literal.</span></span> <span data-ttu-id="a4113-147">Bu nedenle, ortak temel türü olmayan öğelerle bir dizi oluşturmak bir hata oluşturur.</span><span class="sxs-lookup"><span data-stu-id="a4113-147">Hence, constructing an array with elements that have no common base type raises an error.</span></span>  
<span data-ttu-id="a4113-148">Bir örnek için bkz. [callables dizileri](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span><span class="sxs-lookup"><span data-stu-id="a4113-148">For an example, see [arrays of callables](xref:microsoft.quantum.guide.expressions#arrays-of-callables).</span></span>

    > [!WARNING]
    > <span data-ttu-id="a4113-149">Oluşturulduktan sonra bir dizinin öğeleri değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="a4113-149">Once created, the elements of an array cannot be changed.</span></span>
    > <span data-ttu-id="a4113-150">Değiştirilmiş bir dizi oluşturmak için, [Update-and-reassıgn deyimlerini](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) veya [kopyalama ve güncelleştirme ifadelerini](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)kullanın.</span><span class="sxs-lookup"><span data-stu-id="a4113-150">To construct a modified array, use [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span>

* <span data-ttu-id="a4113-151">Alternatif olarak, bir dizi boyutundan `new` anahtar sözcüğü kullanılarak oluşturulabilir:</span><span class="sxs-lookup"><span data-stu-id="a4113-151">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* <span data-ttu-id="a4113-152">Bir `Length` diziden öğe sayısını bir olarak almak için çekirdek işlevini kullanın `Int` .</span><span class="sxs-lookup"><span data-stu-id="a4113-152">Use the core function `Length` to obtain the number of elements from an array as an `Int`.</span></span>
* <span data-ttu-id="a4113-153">Diziler, bir dizinin öğelerinin bir alt kümesini içeren tek öğe veya yeni diziler elde etmek için erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="a4113-153">Arrays can be subscripted to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="a4113-154">Dizilerin alt simgeleri sıfır tabanlıdır ve tür `Int` ya da tür olmalıdır `Range` :</span><span class="sxs-lookup"><span data-stu-id="a4113-154">The subscripts of arrays are zero-based and must be type `Int` or type `Range`:</span></span>

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a><span data-ttu-id="a4113-155">Demet türleri</span><span class="sxs-lookup"><span data-stu-id="a4113-155">Tuple Types</span></span>

<span data-ttu-id="a4113-156">Tanımlama grupları Q# , değerleri tek bir değer toplamak için kullanılan güçlü bir kavramdır, bu da bunları bir araya getirmek daha kolay hale getirir.</span><span class="sxs-lookup"><span data-stu-id="a4113-156">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="a4113-157">Özellikle, tanımlama grubu gösterimini kullanarak her işlemin ve çağrılabilir şekilde tam olarak bir giriş aldığını ve tam olarak bir çıkış döndürdüğünü ifade edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4113-157">In particular, using tuple notation, you can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

* <span data-ttu-id="a4113-158">Sıfır veya daha fazla farklı tür (, `T0` `T1` ...) verildiğinde, `Tn` Yeni bir  *demet türünü* olarak belirtebilirsiniz `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="a4113-158">Given zero or more different types `T0`, `T1`, ..., `Tn`, you can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="a4113-159">Yeni bir demet türü oluşturmak için kullanılan türler, içinde olduğu gibi kendi tanımlama grupları olabilir `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="a4113-159">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="a4113-160">Bu iç içe geçme her zaman sınırlıdır, ancak demet türleri hiçbir koşulda kendilerini içeremez.</span><span class="sxs-lookup"><span data-stu-id="a4113-160">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

* <span data-ttu-id="a4113-161">Yeni demet türünün değerleri, kayıt düzeni içindeki her türden değer dizileri tarafından oluşturulan dizileridir.</span><span class="sxs-lookup"><span data-stu-id="a4113-161">The values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="a4113-162">Örneğin, `(3, false)` türü demet türünde olan bir kayıt türüdür `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="a4113-162">For example, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="a4113-163">Tanımlama dizileri, dizi dizileri, alt tanımlama grupları ve benzeri diziler oluşturmak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="a4113-163">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, and so on.</span></span>

* <span data-ttu-id="a4113-164">0,3 itibariyle Q# , boş tanımlama grubunun `Unit` *türünün* adı, `()` boş tanımlama grubunun *değeri* için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a4113-164">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the *value* of the empty tuple.</span></span>

* <span data-ttu-id="a4113-165">Demet örnekleri sabittir.</span><span class="sxs-lookup"><span data-stu-id="a4113-165">Tuple instances are immutable.</span></span>
<span data-ttu-id="a4113-166">Q# , oluşturulduktan sonra bir kayıt düzeninin içeriğini değiştirme mekanizması sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="a4113-166">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>



### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="a4113-167">Tek kayıt düzeni denklik</span><span class="sxs-lookup"><span data-stu-id="a4113-167">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="a4113-168">Ya da gibi tek bir (tek öğeli) tanımlama grubu oluşturmak mümkündür `('T1)` `(5)` `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="a4113-168">It is possible to create a singleton (single-element) tuple `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="a4113-169">Ancak, Q# tek bir kayıt kümesini, iliştirilmiş türdeki bir değere eşdeğer olarak değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="a4113-169">However, Q# treats a singleton tuple as equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="a4113-170">Diğer bir deyişle, ve arasında ya da ile arasında ya da arasında bir fark yoktur `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="a4113-170">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="a4113-171">Yazmak üzere yazmak için geçerli olduğu gibi, `(5)+3` `5+3` her iki ifade de olarak değerlendirilir `8` .</span><span class="sxs-lookup"><span data-stu-id="a4113-171">It is just as valid to write `(5)+3` as it is to write `5+3`; both expressions evaluate to `8`.</span></span>

<span data-ttu-id="a4113-172">Bu denklik, atama ve ifadeler dahil tüm amaçlar için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="a4113-172">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="a4113-173">Herhangi bir ifade verildiğinde, parantez içine alınmış aynı ifade aynı türde bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="a4113-173">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="a4113-174">Örneğin, türünde bir ifadedir, türünde bir ifadedir `(7)` `Int` `([1,2,3])` `Int[]` ve `((1,2))` türünde bir ifadedir `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="a4113-174">For example, `(7)` is an expression of type `Int`, `([1,2,3])` is an expression of type `Int[]`, and `((1,2))` is an expression of type `(Int, Int)`.</span></span>

<span data-ttu-id="a4113-175">Özellikle, bu, giriş tanımlama grubu veya çıktı kayıt türü türünde tek bir bağımsız değişken alan veya tek bir değer döndüren bir işlem veya işlevi görüntüleyebileceðiniz anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="a4113-175">In particular, this means that you can view an operation or function whose input tuple or output tuple type has one field as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="a4113-176">Bu özelliğe, _tek demet denklik_ olarak başvurduk.</span><span class="sxs-lookup"><span data-stu-id="a4113-176">We refer to this property as _singleton tuple equivalence_ .</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="a4113-177">User-Defined türleri</span><span class="sxs-lookup"><span data-stu-id="a4113-177">User-Defined Types</span></span>

<span data-ttu-id="a4113-178">Kullanıcı tanımlı tür bildirimi, anahtar sözcükten `newtype` , ardından Kullanıcı tanımlı türün adı, bir `=` , geçerli bir tür belirtimi ve sonlandırma noktalı virgülünden oluşur.</span><span class="sxs-lookup"><span data-stu-id="a4113-178">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="a4113-179">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="a4113-179">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* <span data-ttu-id="a4113-180">Her Q# kaynak dosya, Kullanıcı tanımlı herhangi bir sayıda tür bildirebilir.</span><span class="sxs-lookup"><span data-stu-id="a4113-180">Each Q# source file may declare any number of user-defined types.</span></span>
* <span data-ttu-id="a4113-181">Tür adları ad alanı içinde benzersiz olmalıdır ve işlem ve işlev adlarıyla çakışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="a4113-181">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>
* <span data-ttu-id="a4113-182">Temel türler özdeş olsa bile Kullanıcı tanımlı türler farklıdır.</span><span class="sxs-lookup"><span data-stu-id="a4113-182">User-defined types are distinct, even if the base types are identical.</span></span>
<span data-ttu-id="a4113-183">Özellikle, temel alınan türler özdeş olsa bile, iki Kullanıcı tanımlı türün değerleri arasında otomatik dönüşüm yoktur.</span><span class="sxs-lookup"><span data-stu-id="a4113-183">In particular, there is no automatic conversion between the values of two user-defined types, even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="a4113-184">Adlandırılmış vs. Anonymous öğeleri</span><span class="sxs-lookup"><span data-stu-id="a4113-184">Named vs. anonymous items</span></span>

<span data-ttu-id="a4113-185">Bir Q# Dosya, geçerli bir türden tek bir değer içeren yeni bir adlandırılmış tür tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="a4113-185">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="a4113-186">Herhangi bir demet türü için `T` , ifadesiyle birlikte bir alt türü olan yeni bir Kullanıcı tanımlı tür bildirebilirsiniz `T` `newtype` .</span><span class="sxs-lookup"><span data-stu-id="a4113-186">For any tuple type `T`, you can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="a4113-187">@"microsoft.quantum.math"Ad alanında, örneğin, karmaşık sayılar Kullanıcı tanımlı bir tür olarak tanımlanmıştır:</span><span class="sxs-lookup"><span data-stu-id="a4113-187">In the @"microsoft.quantum.math" namespace, for example, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="a4113-188">Bu ifade, türünde iki anonim öğe içeren yeni bir tür oluşturur `Double` .</span><span class="sxs-lookup"><span data-stu-id="a4113-188">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="a4113-189">Anonim öğeler dışında, Kullanıcı tanımlı türler Ayrıca sürüm 0,7 veya üzeri olarak *adlandırılmış öğeleri* destekler Q# .</span><span class="sxs-lookup"><span data-stu-id="a4113-189">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="a4113-190">Örneğin, `Real` bir karmaşık sayının gerçek bölümünü ve sanal parçayı temsil eden Double için öğeleri olarak adlandırın `Imag` :</span><span class="sxs-lookup"><span data-stu-id="a4113-190">For example, you could name the items to `Real` for the double representing the real part of a complex number and `Imag` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Real : Double, Imag : Double);
```
<span data-ttu-id="a4113-191">Kullanıcı tanımlı bir türdeki bir öğenin adlandırılması, tüm öğelerin adlandırılması gerektiğini göstermez; adlandırılmış ve adlandırılmamış öğelerin herhangi bir birleşimi desteklenir.</span><span class="sxs-lookup"><span data-stu-id="a4113-191">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="a4113-192">Ayrıca, iç öğeler de adlandırılmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="a4113-192">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="a4113-193">`Nested`Örneğin, aşağıda tanımlandığı gibi türü, temel bir tür içerir `(Double, (Int, String))` ve yalnızca türü öğe olarak `Int` adlandırılır ve diğer tüm öğeler anonimdir.</span><span class="sxs-lookup"><span data-stu-id="a4113-193">The type `Nested`, as defined below for example, has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named, and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="a4113-194">Adlandırılmış öğeler, *erişim operatörü* aracılığıyla doğrudan erişilebilecekleri avantajına sahiptir `::` .</span><span class="sxs-lookup"><span data-stu-id="a4113-194">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Real + c2::Real, c1::Imag + c2::Imag);
}
```

<span data-ttu-id="a4113-195">Karmaşık tanımlama grubu türleri için kısa diğer adlar sağlamaya ek olarak, böyle türler tanımlamanın önemli bir avantajı, belirli bir değerin amacını belgelememelerdir.</span><span class="sxs-lookup"><span data-stu-id="a4113-195">In addition to providing short aliases for potentially complicated tuple types, a significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="a4113-196">Örneğe dönerek `Complex` , bir tane, Kullanıcı tanımlı tür olarak bir kutupsal koordinat gösterilemeyen de tanımlanabilir:</span><span class="sxs-lookup"><span data-stu-id="a4113-196">Returning to the example of `Complex`, one could have also defined a polar coordinate represenation as a user-defined type:</span></span>

```qsharp
newtype ComplexPolar = (Magnitude : Double, Argument : Double);
```

<span data-ttu-id="a4113-197">Hem hem de `Complex` `ComplexPolar` her ikisi de temel bir türe sahip olsa da `(Double, Double)` , iki tür ' de tamamen uyumsuz Q# , yanlışlıkla bir karmaşık matematik işlevini kutupsal koordinatlarla çağırma riskini en aza indirir ve tam tersi de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="a4113-197">Even though both `Complex` and `ComplexPolar` both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="a4113-198">Unwrap işleci ile anonim öğelere erişme</span><span class="sxs-lookup"><span data-stu-id="a4113-198">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="a4113-199">Anonim öğelere erişmek için önce sonek işlecini kullanarak sarmalanmış değeri ayıklayın `!` .</span><span class="sxs-lookup"><span data-stu-id="a4113-199">To access anonymous items, first extract the wrapped value using the postfix operator `!`.</span></span>
<span data-ttu-id="a4113-200">"Sarmalama" işleci ile, `!` Kullanıcı tanımlı bir türde bulunan değeri ayıklayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4113-200">With the "unwrap" operator, `!`, you can extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="a4113-201">Böyle bir "sarmalama" ifadesinin türü, Kullanıcı tanımlı türün temel türüdür.</span><span class="sxs-lookup"><span data-stu-id="a4113-201">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="a4113-202">Tek sarmalama işleci bir sarmalama katmanının sarmalanmasını kaldırır.</span><span class="sxs-lookup"><span data-stu-id="a4113-202">A single unwrap operator unwraps one layer of wrapping.</span></span> <span data-ttu-id="a4113-203">Çarpmadan kaydırılmış bir değere erişmek için birden çok sarmalama işleci kullanın.</span><span class="sxs-lookup"><span data-stu-id="a4113-203">Use multiple unwrap operators to access a multiply-wrapped value.</span></span>

<span data-ttu-id="a4113-204">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="a4113-204">For example:</span></span>

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

<span data-ttu-id="a4113-205">Unwrap işleci hakkında daha fazla bilgi için bkz. [Içindeki Q# tür ifadeleri ](xref:microsoft.quantum.guide.expressions).</span><span class="sxs-lookup"><span data-stu-id="a4113-205">For more details on the unwrap operator, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="a4113-206">Kullanıcı tanımlı türlerin değerlerini oluşturma</span><span class="sxs-lookup"><span data-stu-id="a4113-206">Creating values of user-defined types</span></span>

<span data-ttu-id="a4113-207">Karşılık gelen tür oluşturucusunu çağırarak Kullanıcı tanımlı bir türün değerlerini oluşturun:</span><span class="sxs-lookup"><span data-stu-id="a4113-207">Create values of a user-defined type by calling the corresponding type constructor:</span></span>

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="a4113-208">Alternatif olarak, [kopyalama ve güncelleştirme ifadelerini](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)kullanarak var olan olanlardan yeni değerler oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4113-208">Alternatively, you can create new values from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="a4113-209">Diziler ile yaptığı gibi, kopyalama ve güncelleştirme ifadeleri, belirtilen adlandırılmış öğeler hariç özgün ifadenin tüm öğe değerlerini kopyalar.</span><span class="sxs-lookup"><span data-stu-id="a4113-209">Just as they do with arrays, copy-and-update expressions copy all item values of the original expression, except for the specified named items.</span></span> <span data-ttu-id="a4113-210">Bu özel durumlar için, bu öğelerin değerleri, ifadenin sağ tarafında tanımlanan değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="a4113-210">For these exceptions, the values of these items are the values defined on the right-hand side of the expression.</span></span> <span data-ttu-id="a4113-211">Dizi öğeleri için kullanılabilen diğer dil yapıları (örneğin, [Update ve-yeniden atama deyimleri](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)), Kullanıcı tanımlı türlerde adlandırılmış öğeler için de mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="a4113-211">Any other language constructs that are available for array items, for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), exist for named-items in user-defined types as well.</span></span>

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

* <span data-ttu-id="a4113-212">Kullanıcı tanımlı türleri başka herhangi bir türü kullandığınız her yerde kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4113-212">You can use user-defined types anywhere you use any other types.</span></span>
<span data-ttu-id="a4113-213">Özellikle, Kullanıcı tanımlı bir türün dizisini tanımlamak ve Kullanıcı tanımlı bir türü bir demet türünün öğesi olarak eklemek mümkündür.</span><span class="sxs-lookup"><span data-stu-id="a4113-213">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

* <span data-ttu-id="a4113-214">Özyinelemeli tür yapıları oluşturmak mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="a4113-214">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="a4113-215">Diğer bir deyişle, Kullanıcı tanımlı bir türü tanımlayan tür, Kullanıcı tanımlı türdeki bir öğeyi içeren bir demet türü olamaz.</span><span class="sxs-lookup"><span data-stu-id="a4113-215">That is, the type that defines a user-defined type cannot be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="a4113-216">Daha genel olarak, Kullanıcı tanımlı türlerin birbirlerine döngüsel bağımlılıkları olmayabilir, bu nedenle aşağıdaki tür tanımları kümesi geçersizdir:</span><span class="sxs-lookup"><span data-stu-id="a4113-216">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions are invalid:</span></span>

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a><span data-ttu-id="a4113-217">İşlem ve Işlev türleri</span><span class="sxs-lookup"><span data-stu-id="a4113-217">Operation and Function Types</span></span>

<span data-ttu-id="a4113-218">Türler `'Tinput` ve `'Tresult` :</span><span class="sxs-lookup"><span data-stu-id="a4113-218">Given the types `'Tinput` and `'Tresult`:</span></span>

* <span data-ttu-id="a4113-219">`('Tinput => 'Tresult)` , örneğin, her bir *işlemin* temel türüdür `((Qubit, Pauli) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="a4113-219">`('Tinput => 'Tresult)` is the basic type for any *operation* , for example `((Qubit, Pauli) => Result)`.</span></span>
* <span data-ttu-id="a4113-220">`('Tinput -> 'Tresult)` , örneğin, herhangi bir *işlevin* temel türüdür `(Int -> Int)` .</span><span class="sxs-lookup"><span data-stu-id="a4113-220">`('Tinput -> 'Tresult)` is the basic type for any *function* , for example `(Int -> Int)`.</span></span> 

<span data-ttu-id="a4113-221">Bunlara çağrılabilir *imzası* denir.</span><span class="sxs-lookup"><span data-stu-id="a4113-221">These are called the *signature* of the callable.</span></span>

* <span data-ttu-id="a4113-222">Tüm Q# callables, girdi olarak tek bir değer alır ve çıkış olarak tek bir değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="a4113-222">All Q# callables take a single value as input and return a single value as output.</span></span>
* <span data-ttu-id="a4113-223">Hem giriş hem de çıkış değerleri için tanımlama grupları kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a4113-223">You can use tuples for both the input and output values.</span></span>
* <span data-ttu-id="a4113-224">Sonuç içermeyen callables, döndürün `Unit` .</span><span class="sxs-lookup"><span data-stu-id="a4113-224">Callables that have no result, return `Unit`.</span></span>
* <span data-ttu-id="a4113-225">Girişi olmayan callables, boş kayıt grubunu giriş olarak alır.</span><span class="sxs-lookup"><span data-stu-id="a4113-225">Callables that have no input take the empty tuple as input.</span></span>

### <a name="functors"></a><span data-ttu-id="a4113-226">Functorları</span><span class="sxs-lookup"><span data-stu-id="a4113-226">Functors</span></span>

<span data-ttu-id="a4113-227">*İşlev* türleri kendi imzasıyla tamamen belirtilir.</span><span class="sxs-lookup"><span data-stu-id="a4113-227">*Function* types are completely specified by their signature.</span></span> <span data-ttu-id="a4113-228">Örneğin, bir açının sinüsünü hesaplayan bir işlev türünde olabilir `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="a4113-228">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span> 

<span data-ttu-id="a4113-229">*İşlemler* , işlem türünün bir parçası olarak ifade edilen bazı ek özelliklere sahiptir.</span><span class="sxs-lookup"><span data-stu-id="a4113-229">*Operations* have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="a4113-230">Bu tür özellikler, işlemin desteklediği *komik* ilgili bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="a4113-230">Such characteristics include information about which *functors* the operation supports.</span></span>
<span data-ttu-id="a4113-231">Örneğin, işlemin çalıştırılması diğer qubits 'in durumuna dayanıyorsa, bu durumda `Controlled` functor 'ı desteklemelidir; işlemin bir ters olması halinde, functor 'ı desteklemesi gerekir `Adjoint` .</span><span class="sxs-lookup"><span data-stu-id="a4113-231">For example, if the running of the operation relies on the state of other qubits, then it should support the `Controlled` functor; if the operation has an inverse, then it should support the `Adjoint` functor.</span></span>

> [!NOTE]
> <span data-ttu-id="a4113-232">Bu makalede, yalnızca funörler işlem imzasını nasıl değiştirtiğiyle tartışılmaz.</span><span class="sxs-lookup"><span data-stu-id="a4113-232">This article only discuss how functors alter the operation signature.</span></span> <span data-ttu-id="a4113-233">Komik ve işlemler hakkında daha fazla bilgi için bkz. [Içindeki Q# Işlemler ve işlevler ](xref:microsoft.quantum.guide.operationsfunctions).</span><span class="sxs-lookup"><span data-stu-id="a4113-233">For more details about functors and operations, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span> 

<span data-ttu-id="a4113-234">`Controlled`Bir işlem türünde ve/veya functor desteğinin gerekli olmasını sağlamak için `Adjoint` , karşılık gelen özellikleri belirten bir ek açıklama eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="a4113-234">To require support for the `Controlled` and/or `Adjoint` functor in an operation type, you need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="a4113-235">Ek açıklama `is Ctl` (örneğin, `(Qubit => Unit is Ctl)` ), işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="a4113-235">The annotation `is Ctl` (for example, `(Qubit => Unit is Ctl)`) indicates that the operation is controllable.</span></span> <span data-ttu-id="a4113-236">Diğer bir deyişle, çalıştırması başka bir qubit veya qubits 'in durumuna bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="a4113-236">That is, its run relies on the state of another qubit or qubits.</span></span> <span data-ttu-id="a4113-237">Benzer şekilde, ek açıklama `is Adj` işlemin bir adeklem olduğunu, yani "ters" (bir işlem) ve ardından adjoint değerini bir durum olduğu gibi bırakır.</span><span class="sxs-lookup"><span data-stu-id="a4113-237">Similarly, the annotation `is Adj` indicates that the operation has an adjoint, that is, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="a4113-238">Bu tür bir işlemin hem hem de functor desteklediğinden emin olmak istiyorsanız `Adjoint` `Controlled` bunu olarak ifade edebilirsiniz `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="a4113-238">If you want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor you can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="a4113-239">Örneğin, yerleşik Pauli <xref:Microsoft.Quantum.Intrinsic.X> işleminin türü vardır `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="a4113-239">For example, the built-in Pauli <xref:Microsoft.Quantum.Intrinsic.X> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="a4113-240">Herhangi bir belirtiyi desteklemeyen bir işlem türü, giriş ve çıkış türü ile tek başına, ek açıklama olmadan belirtilir.</span><span class="sxs-lookup"><span data-stu-id="a4113-240">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="a4113-241">Type-Parameterized Işlevleri ve Işlemler</span><span class="sxs-lookup"><span data-stu-id="a4113-241">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="a4113-242">Çağrılabilir türler *tür parametreleri* içerebilir.</span><span class="sxs-lookup"><span data-stu-id="a4113-242">Callable types may contain *type parameters* .</span></span>
<span data-ttu-id="a4113-243">Bir tür parametresi belirtilen tek tırnak tarafından önekli bir sembol kullanın; Örneğin, `'A` yasal bir tür parametresidir.</span><span class="sxs-lookup"><span data-stu-id="a4113-243">Use a symbol prefixed by a single quote to indicated a type parameter; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="a4113-244">Tür parametreli callables tanımlama hakkında daha fazla bilgi ve Ayrıntılar için bkz. [Içindeki Q# Işlemler ve işlevler ](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span><span class="sxs-lookup"><span data-stu-id="a4113-244">For more information and details on how to define type-parameterized callables, see [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables).</span></span>

<span data-ttu-id="a4113-245">Bir tür parametresi, tek bir imzada birden çok kez görünebilir.</span><span class="sxs-lookup"><span data-stu-id="a4113-245">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="a4113-246">Örneğin, bir dizinin her öğesine başka bir işlev uygulayan ve toplanan sonuçların imzasını döndüren bir işlev `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="a4113-246">For example, a function that applies another function to each element of an array and returns the collected results has the signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="a4113-247">Benzer şekilde, iki işlemin birleşimini döndüren bir işlev imzaya sahiptir `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="a4113-247">Similarly, a function that returns the composition of two operations has the signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="a4113-248">Parametreli bir tür türü çağırdığınızda, aynı tür parametresine sahip olan tüm bağımsız değişkenler aynı türde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a4113-248">When you invoke a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="a4113-249">Q# , bir kullanıcının bir tür parametresi için yerine geçecek olası türleri kısıtlayan bir mekanizma sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="a4113-249">Q# does not provide a mechanism for constraining the possible types that a user might substitute for a type parameter.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a4113-250">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="a4113-250">Next steps</span></span>

<span data-ttu-id="a4113-251">Dili oluşturan tüm türleri gördüğünüze Q# göre, bu çeşitli türlerin ifadelerini oluşturmayı ve işlemeyi öğrenmek için [Içindeki Q# tür ifadeleri](xref:microsoft.quantum.guide.expressions) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="a4113-251">Now that you've seen all the types which comprise the Q# language, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to learn how to create and manipulate expressions of these various types.</span></span>
