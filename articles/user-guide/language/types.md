---
title: Q# dilindeki türler
description: 'Q # programlama dilinde kullanılan farklı türler hakkında bilgi edinin.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: 4a551ee90a0abb6e42953cf04c7f5a8ca3573f26
ms.sourcegitcommit: 682a4a5f5dd23ca58a4addf62aea4086bb308552
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609150"
---
# <a name="types-in-q"></a><span data-ttu-id="1ba95-103">Q# dilindeki türler</span><span class="sxs-lookup"><span data-stu-id="1ba95-103">Types in Q#</span></span>

<span data-ttu-id="1ba95-104">Bu sayfa, Q # tür modelini yerleştirir ve türleri belirtmek ve bunlarla çalışmak için sözdizimini açıklar.</span><span class="sxs-lookup"><span data-stu-id="1ba95-104">This page lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="1ba95-105">Sonraki sayfa, [tür ifadeleri](xref:microsoft.quantum.guide.expressions), bu türlerin ifadeleri oluşturma ve üzerinde işlem yapma ayrıntıları.</span><span class="sxs-lookup"><span data-stu-id="1ba95-105">The next page, [Type Expressions](xref:microsoft.quantum.guide.expressions), details how to create and operate on expressions of these types.</span></span>

<span data-ttu-id="1ba95-106">Bu tür dikkatle kullanılması derleyicinin, derleme zamanında Q # programları hakkında güçlü garantiler sağlamasına yardımcı olabileceğini belirten, *kesin olarak yazılmış* bir dil olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="1ba95-106">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="1ba95-107">Mümkün olan en güçlü garantiyi sağlamak için, Q # içindeki türler arasındaki dönüştürmeler, bu dönüştürmeyi ifade eden işlevlere yapılan çağrılar kullanılarak açık olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-107">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="1ba95-108">Bu gibi çeşitli işlevler, ad alanının bir parçası olarak sağlanır <xref:microsoft.quantum.convert> .</span><span class="sxs-lookup"><span data-stu-id="1ba95-108">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="1ba95-109">Diğer yandan uyumlu türlere yapılan yayınlar örtülü olarak gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-109">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="1ba95-110">Q #, doğrudan kullanılabilen basit türler ve diğer türlerden yeni türler oluşturmak için çeşitli yollar sağlar.</span><span class="sxs-lookup"><span data-stu-id="1ba95-110">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="1ba95-111">Bu bölümün geri kalanında her birini açıklıyoruz.</span><span class="sxs-lookup"><span data-stu-id="1ba95-111">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="1ba95-112">İlkel Türler</span><span class="sxs-lookup"><span data-stu-id="1ba95-112">Primitive Types</span></span>

<span data-ttu-id="1ba95-113">Q # dili, diğer türlerin oluşturulabileceği çeşitli *temel türler*sağlar:</span><span class="sxs-lookup"><span data-stu-id="1ba95-113">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="1ba95-114">`Int`Tür, 64 bitlik işaretli bir tamsayıyı temsil eder, örneğin: `2` , `107` , `-5` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-114">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="1ba95-115">`BigInt`Tür, rastgele boyutun işaretli bir tamsayı temsil eder, örneğin, `2L` `107L` `-5L` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-115">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="1ba95-116">Bu tür .NET tabanlıdır<xref:System.Numerics.BigInteger></span><span class="sxs-lookup"><span data-stu-id="1ba95-116">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="1ba95-117">türüyle.</span><span class="sxs-lookup"><span data-stu-id="1ba95-117">type.</span></span>
- <span data-ttu-id="1ba95-118">`Double`Tür çift duyarlıklı kayan noktalı sayıyı temsil eder, örneğin: `0.0` , `-1.3` , `4e-7` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-118">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="1ba95-119">`Bool`Tür ya da olabilecek bir Boolean değeri temsil eder `true` `false` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-119">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="1ba95-120">`Range`Türü, tarafından belirtilen, `start..step..stop` adımın isteğe bağlı olduğunu gösteren bir tamsayılar dizisini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="1ba95-120">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is optional.</span></span> 
   <span data-ttu-id="1ba95-121">Bu `start .. stop` öğesine karşılık gelir `start..1..stop` ve örn. `1..2..7` $ \{ 1, 3, 5, 7 $ dizisini temsil eder \} .</span><span class="sxs-lookup"><span data-stu-id="1ba95-121">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="1ba95-122">`String`Tür, bir kez oluşturulduktan sonra kullanıcıya donuk olan Unicode karakterlerinden oluşan bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-122">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="1ba95-123">Bu tür, bir hata veya tanılama olayı durumunda iletileri klasik bir konağa raporlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-123">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="1ba95-124">`Unit`Tür yalnızca bir değere izin veren türdür `()` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-124">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="1ba95-125">Bu tür, Q # işlevinin veya işleminin hiçbir bilgi döndürdüğünü göstermek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-125">This type is used to indicate that Q# function or operation returns no information.</span></span> 
- <span data-ttu-id="1ba95-126">`Qubit`Tür bir hisse bitini veya qubit 'i temsil eder.</span><span class="sxs-lookup"><span data-stu-id="1ba95-126">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="1ba95-127">`Qubit`, kullanıcının opaktır; Bunlar ile mümkün olan tek işlem, başka bir işleme geçirilmekten farklı kimlik (eşitlik) için test amaçlıdır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-127">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="1ba95-128">Sonuç olarak, içindeki eylemler `Qubit` bir hisse işlemcisi (veya bir simülasyonu) üzerinde iç yönergeler çağırarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-128">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="1ba95-129">`Pauli`Tür, dört adet tek qubit Pauli işleçlerinden birini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="1ba95-129">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="1ba95-130">Bu tür, döndürmeler için temel işlemi göstermek ve ölçülecek observable 'ı belirtmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-130">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="1ba95-131">Bu, dört olası değeri olan numaralandırılmış bir türdür: `PauliI` ,, `PauliX` `PauliY` , ve `PauliZ` , türünde sabitler `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-131">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="1ba95-132">`Result`Tür, ölçümün sonucunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="1ba95-132">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="1ba95-133">Bu, iki olası değeri olan `One` ve türünde sabitler olan numaralandırılmış bir türdür `Zero` `Result` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-133">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="1ba95-134">`Zero`+ 1 eigenvalue değerinin ölçüldüğünü belirtir; `One`-1 eigenvalue değerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-134">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>

<span data-ttu-id="1ba95-135">,,,,,, Ve sabitleri, `true` `false` `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` Q # içinde tüm ayrılmış sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-135">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="1ba95-136">Dizi türleri</span><span class="sxs-lookup"><span data-stu-id="1ba95-136">Array Types</span></span>

<span data-ttu-id="1ba95-137">Geçerli bir Q # türü verildiğinde `'T` , türünde bir değer dizisini temsil eden bir tür vardır `'T` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-137">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="1ba95-138">Bu dizi türü olarak temsil edilir `'T[]` ; Örneğin, `Qubit[]` veya `Int[][]` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-138">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="1ba95-139">Örneğin, bir tamsayılar koleksiyonu gösterilir `Int[]` , ancak değer dizileri dizisi `(Bool, Pauli)` gösterilir `(Bool, Pauli)[][]` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-139">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="1ba95-140">İkinci örnekte bunun, dikdörtgen iki boyutlu bir dizi değil, potansiyel olarak pürüzlü dizi dizileri temsil ettiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="1ba95-140">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="1ba95-141">Q #, dikdörtgen çok boyutlu diziler için destek sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="1ba95-141">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="1ba95-142">Bir dizi değeri, içinde olduğu gibi bir dizinin öğeleri etrafında köşeli parantezler kullanılarak Q # kaynak kodunda yazılabilir `[PauliI, PauliX, PauliY, PauliZ]` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-142">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="1ba95-143">Dizi sabit değerinin türü dizideki tüm öğelerin ortak temel türüne göre belirlenir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-143">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="1ba95-144">Dizinin öğeleri, dizi oluşturulduktan sonra değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="1ba95-144">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="1ba95-145">[Güncelleştirme ve yeniden atama deyimleri](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) ve/veya [kopyalama ve güncelleştirme ifadeleri](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) , değiştirilmiş bir diziyi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-145">[Update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements) and/or [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) can be used to construct a modified array.</span></span>

<span data-ttu-id="1ba95-146">Alternatif olarak, bir dizi boyutundan `new` anahtar sözcüğü kullanılarak oluşturulabilir:</span><span class="sxs-lookup"><span data-stu-id="1ba95-146">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="1ba95-147">Her iki durumda da, bir dizi oluşturulduktan sonra, temel işlev `Length` öğe sayısını bir olarak almak için kullanılabilir `Int` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-147">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="1ba95-148">Diziler, `Int` `Range` bir dizinin öğelerinin bir alt kümesini içeren tek öğe veya yeni diziler elde etmek için tür veya tür içeren alt simgeler ile köşeli ayraç kullanılarak alt simge olabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-148">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="1ba95-149">Dizilerin alt simgeleri sıfır tabanlıdır:</span><span class="sxs-lookup"><span data-stu-id="1ba95-149">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="1ba95-150">Demet türleri</span><span class="sxs-lookup"><span data-stu-id="1ba95-150">Tuple Types</span></span>

<span data-ttu-id="1ba95-151">Sıfır veya daha fazla farklı tür (, `T0` `T1` ...) verildiğinde `Tn` Yeni bir *demet türü* olarak belirtilebilir `(T0, T1, ..., Tn)` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-151">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="1ba95-152">Yeni bir demet türü oluşturmak için kullanılan türler, içinde olduğu gibi kendi tanımlama grupları olabilir `(Int, (Qubit, Qubit))` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-152">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="1ba95-153">Bu iç içe geçme her zaman sınırlıdır, ancak demet türleri hiçbir koşulda kendilerini içeremez.</span><span class="sxs-lookup"><span data-stu-id="1ba95-153">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="1ba95-154">Yeni demet türünün değerleri, kayıt düzeni içindeki her türden değer dizileri tarafından oluşturulan dizileridir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-154">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="1ba95-155">Örneğin, `(3, false)` türü demet türünde olan bir kayıt türüdür `(Int, Bool)` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-155">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="1ba95-156">Tanımlama dizileri, dizi dizilerindeki diziler, alt tanımlama grupları, vb. öğeleri oluşturmak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="1ba95-156">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="1ba95-157">Q # 0,3 itibariyle, boş kayıt düzeni `Unit` *türünün* adı, boş demet `()` *değeri*için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-157">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="1ba95-158">Demet örnekleri sabittir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-158">Tuple instances are immutable.</span></span>
<span data-ttu-id="1ba95-159">S #, oluşturulduktan sonra bir kayıt düzeninin içeriğini değiştirme mekanizması sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="1ba95-159">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="1ba95-160">Tanımlama grupları, her bir değer toplamak için Q # boyunca kullanılan güçlü bir kavramdır; bu da, daha kolay bir şekilde geçiş yapmayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-160">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="1ba95-161">Özellikle, tanımlama grubu gösterimini kullanarak her işlemin ve çağrılabilir şekilde tam olarak bir giriş aldığını ve tam olarak bir çıkış döndürdüğünü ifade edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1ba95-161">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="1ba95-162">Tek kayıt düzeni denklik</span><span class="sxs-lookup"><span data-stu-id="1ba95-162">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="1ba95-163">Veya gibi tek bir (tek öğeli) tanımlama grubu oluşturmak mümkündür `('T1)` `(5)` `([1,2,3])` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-163">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="1ba95-164">Ancak, Q #, tek bir kayıt kümesini, iliştirilmiş türdeki bir değere tamamen eşdeğer olarak değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-164">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="1ba95-165">Diğer bir deyişle, ve arasında ya da ile arasında ya da arasında bir fark yoktur `5` `(5)` `5` `(((5)))` `(5, (6))` `(5, 6)` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-165">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>
<span data-ttu-id="1ba95-166">Yazmak üzere yazmak için geçerli olduğu gibi `(5)+3` `5+3` , her iki ifade de olarak değerlendirilir `8` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>

<span data-ttu-id="1ba95-167">Bu denklik, atama ve ifadeler dahil tüm amaçlar için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-167">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="1ba95-168">Herhangi bir ifade verildiğinde, parantez içine alınmış aynı ifade aynı türde bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-168">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="1ba95-169">Örneğin, `(7)` bir ifadedir, `Int` `([1,2,3])` dizi türünde bir ifadedir `Int` ve `((1,2))` türünde bir ifadedir `(Int, Int)` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-169">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="1ba95-170">Özellikle, bu, giriş kümesi veya çıkış grubu türü olan bir işlemin veya işlevin tek bir bağımsız değişken alan veya tek bir değer döndüren bir alana sahip olabileceği anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-170">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="1ba95-171">Bu özelliğe, _tek demet denklik_olarak başvurduk.</span><span class="sxs-lookup"><span data-stu-id="1ba95-171">We refer to this property as _singleton tuple equivalence_.</span></span>


## <a name="user-defined-types"></a><span data-ttu-id="1ba95-172">Kullanıcı tanımlı türler</span><span class="sxs-lookup"><span data-stu-id="1ba95-172">User-Defined Types</span></span>

<span data-ttu-id="1ba95-173">Kullanıcı tanımlı tür bildirimi, anahtar sözcükten `newtype` , ardından Kullanıcı tanımlı türün adı, bir `=` , geçerli bir tür belirtimi ve sonlandırma noktalı virgülünden oluşur.</span><span class="sxs-lookup"><span data-stu-id="1ba95-173">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="1ba95-174">Örnek:</span><span class="sxs-lookup"><span data-stu-id="1ba95-174">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="1ba95-175">Her Q # kaynak dosyası herhangi bir sayıda kullanıcı tanımlı tür bildirebilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-175">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="1ba95-176">Tür adları ad alanı içinde benzersiz olmalıdır ve işlem ve işlev adlarıyla çakışmayabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-176">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="1ba95-177">Temel türler özdeş olsa bile Kullanıcı tanımlı türler farklıdır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-177">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="1ba95-178">Özellikle, temeldeki türler özdeş olsa bile, iki Kullanıcı tanımlı türün değerleri arasında otomatik dönüşüm yoktur.</span><span class="sxs-lookup"><span data-stu-id="1ba95-178">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

### <a name="named-vs-anonymous-items"></a><span data-ttu-id="1ba95-179">Adlandırılmış vs. Anonymous öğeleri</span><span class="sxs-lookup"><span data-stu-id="1ba95-179">Named vs. anonymous items</span></span>

<span data-ttu-id="1ba95-180">Bir Q # dosyası, geçerli bir türden tek bir değer içeren yeni bir adlandırılmış tür tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-180">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="1ba95-181">Herhangi bir demet türü için `T` , ifadesiyle birlikte bir alt türü olan yeni bir Kullanıcı tanımlı tür bildirebiliriz `T` `newtype` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-181">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="1ba95-182">@"microsoft.quantum.math"Ad alanında, örneğin, karmaşık sayılar Kullanıcı tanımlı bir tür olarak tanımlanmıştır:</span><span class="sxs-lookup"><span data-stu-id="1ba95-182">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```
<span data-ttu-id="1ba95-183">Bu ifade, türünde iki anonim öğe içeren yeni bir tür oluşturur `Double` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-183">This statement creates a new type with two anonymous items of type `Double`.</span></span>   

<span data-ttu-id="1ba95-184">Anonim öğeler dışında, Kullanıcı tanımlı türler Ayrıca, Q # sürüm 0,7 veya üzeri olarak *adlandırılmış öğeleri* de destekler.</span><span class="sxs-lookup"><span data-stu-id="1ba95-184">Aside from anonymous items, user-defined types also support *named items* as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="1ba95-185">Örneğin, `Re` bir karmaşık sayının gerçek bölümünü ve sanal parçayı temsil eden Double için öğeleri olarak adlandırdık `Im` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-185">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="1ba95-186">Kullanıcı tanımlı bir türdeki bir öğenin adlandırılması, tüm öğelerin adlandırılması gerektiğini göstermez; adlandırılmış ve adlandırılmamış öğelerin herhangi bir birleşimi desteklenir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-186">Naming one item in a user-defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="1ba95-187">Ayrıca, iç öğeler de adlandırılmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-187">Furthermore, inner items may also be named.</span></span>
<span data-ttu-id="1ba95-188">`Nested`Aşağıda tanımlanan türün temel bir türü vardır `(Double, (Int, String))` ; yalnızca türü öğe `Int` ve diğer tüm öğeler anonim olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-188">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

<span data-ttu-id="1ba95-189">Adlandırılmış öğeler, *erişim operatörü* aracılığıyla doğrudan erişilebilecekleri avantajına sahiptir `::` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-189">Named items have the advantage that they can be accessed directly via the *access operator* `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="1ba95-190">Karmaşık tanımlama grubu türleri için kısa diğer adlar sağlamaya ek olarak, bu tür türler tanımlamanın önemli bir avantajı, belirli bir değerin amacını belgelememelerdir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-190">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="1ba95-191">Örneğe dönerek `Complex` , bir Kullanıcı tanımlı tür olarak 2B kutupsal koordinatları de tanımlanabilir:</span><span class="sxs-lookup"><span data-stu-id="1ba95-191">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="1ba95-192">Hem hem de her ikisi de temel bir türe sahip olsa da, iki tür, her ikisi de, her ikisi de `Complex` `Polar` aynı şekilde soru-cevap olarak `(Double, Double)` bir karmaşık matematik işlevini çağırma riskini en aza indirir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-192">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="1ba95-193">Bu şekilde, Kullanıcı tanımlı türlerin F # ' ta kayıt olarak benzer bir rolü vardır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-193">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a><span data-ttu-id="1ba95-194">Unwrap işleci ile anonim öğelere erişme</span><span class="sxs-lookup"><span data-stu-id="1ba95-194">Access anonymous items with the unwrap operator</span></span>

<span data-ttu-id="1ba95-195">Diğer yandan anonim öğelere erişmek için, Sarmalanan değerin ilk olarak sonek işleci kullanılarak ayıklanabilmesi gerekir `!` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-195">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="1ba95-196">"Unwrap" işleci, `!` Kullanıcı tanımlı bir türde bulunan değeri ayıklamasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-196">The "unwrap" operator, `!`, allows to extract the value contained in a user-defined type.</span></span>
<span data-ttu-id="1ba95-197">Böyle bir "sarmalama" ifadesinin türü, Kullanıcı tanımlı türün temel türüdür.</span><span class="sxs-lookup"><span data-stu-id="1ba95-197">The type of such an "unwrap" expression is the underlying type of the user-defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="1ba95-198">Unwrap işleci, tam olarak bir sarmalama katmanını sarmalanmış olarak kaldırır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-198">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="1ba95-199">Çarpma sarmalanmış bir değere erişmek için birden çok sarmalama işleci kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-199">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="1ba95-200">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="1ba95-200">For instance:</span></span>

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

<span data-ttu-id="1ba95-201">Unwrap işleci hakkında daha fazla ayrıntı, [Q # Içindeki tür ifadelerinde](xref:microsoft.quantum.guide.expressions)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-201">More details on the unwrap operator can be found at [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span>

### <a name="creating-values-of-user-defined-types"></a><span data-ttu-id="1ba95-202">Kullanıcı tanımlı türlerin değerlerini oluşturma</span><span class="sxs-lookup"><span data-stu-id="1ba95-202">Creating values of user-defined types</span></span>

<span data-ttu-id="1ba95-203">Kullanıcı tanımlı bir türün değerleri, karşılık gelen tür Oluşturucusu çağırarak oluşturulabilir:</span><span class="sxs-lookup"><span data-stu-id="1ba95-203">Values of a user-defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="1ba95-204">Alternatif olarak, [kopyalama ve güncelleştirme ifadeleri](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)kullanılarak mevcut olanlardan yeni değerler oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-204">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="1ba95-205">Diziler gibi ifadeler, özgün ifadenin tüm öğe değerlerini, belirtilen adlandırılmış öğelerin özel durumuyla birlikte kopyalar.</span><span class="sxs-lookup"><span data-stu-id="1ba95-205">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="1ba95-206">Bu değerler için, ifadenin sağ tarafında tanımlananlara ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-206">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="1ba95-207">Aynı zamanda, Kullanıcı tanımlı türlerde adlandırılmış öğeler için kullanılabilen, örneğin [Update-ve-yeniden atama deyimleri](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)gibi diğer dil yapıları de mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="1ba95-207">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.guide.variables#update-and-reassign-statements), that are available for array items exist for named-items in user-defined types as well.</span></span>

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

<span data-ttu-id="1ba95-208">Kullanıcı tanımlı türler, diğer herhangi bir tür kullanılabilir her yerde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-208">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="1ba95-209">Özellikle, Kullanıcı tanımlı bir türün dizisini tanımlamak ve Kullanıcı tanımlı bir türü bir demet türünün öğesi olarak eklemek mümkündür.</span><span class="sxs-lookup"><span data-stu-id="1ba95-209">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="1ba95-210">Özyinelemeli tür yapıları oluşturmak için Not mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-210">Note is not possible to create recursive type structures.</span></span>
<span data-ttu-id="1ba95-211">Diğer bir deyişle, Kullanıcı tanımlı bir türü tanımlayan tür, Kullanıcı tanımlı türdeki bir öğe içeren bir demet türü olamaz.</span><span class="sxs-lookup"><span data-stu-id="1ba95-211">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="1ba95-212">Daha genel olarak, Kullanıcı tanımlı türlerin birbirlerine döngüsel bağımlılıkları olmayabilir, bu nedenle aşağıdaki tür tanımları kümesi geçersizdir:</span><span class="sxs-lookup"><span data-stu-id="1ba95-212">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```


## <a name="operation-and-function-types"></a><span data-ttu-id="1ba95-213">İşlem ve Işlev türleri</span><span class="sxs-lookup"><span data-stu-id="1ba95-213">Operation and Function Types</span></span>

<span data-ttu-id="1ba95-214">Çağrılabilir her ikisi için temel tür veya olarak yazılır `('Tinput => 'Tresult)` ; `('Tinput -> 'Tresult)` burada `'Tinput` ve `'Tresult` türleri.</span><span class="sxs-lookup"><span data-stu-id="1ba95-214">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="1ba95-215">Bunlara çağrılabilir *imzası* denir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-215">These are called the *signature* of the callable.</span></span>

<span data-ttu-id="1ba95-216">Tüm Q # callables, giriş olarak tek bir değer alıp çıkış olarak tek bir değer döndürecek şekilde değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-216">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="1ba95-217">Hem giriş hem de çıkış değerleri tanımlama grupları olabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-217">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="1ba95-218">Sonuç dönüşü olmayan callables `Unit` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-218">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="1ba95-219">Girişi olmayan callables, boş kayıt grubunu giriş olarak alır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-219">Callables that have no input take the empty tuple as input.</span></span>

> [!NOTE]
> <span data-ttu-id="1ba95-220">İle ilk form, `=>` işlemler için kullanılır; ikinci form, ile, `->` işlevleri için.</span><span class="sxs-lookup"><span data-stu-id="1ba95-220">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
> <span data-ttu-id="1ba95-221">Örneğin, `((Qubit, Pauli) => Result)` olası bir tek qubit ölçüm işleminin imzasını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="1ba95-221">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>
<span data-ttu-id="1ba95-222">*İşlev* türleri kendi imzasıyla tamamen belirtilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-222">*Function* types are completely specified by their signature.</span></span>
<span data-ttu-id="1ba95-223">Örneğin, bir açının sinüsünü hesaplayan bir işlev türünde olabilir `(Double -> Double)` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-223">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="1ba95-224">*İşlemler*---, ancak işlevleri---, işlem türünün bir parçası olarak ifade edilen bazı ek özelliklere sahiptir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-224">*Operations*---but not functions---have certain additional characteristics that are expressed as part of the operation type.</span></span> <span data-ttu-id="1ba95-225">Bu tür özellikler, işlemin desteklediği *komik* ilgili bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-225">Such characteristics include information about what *functors* the operation supports.</span></span>
<span data-ttu-id="1ba95-226">Örneğin, işlemin yürütülmesi diğer qubit durumlarına göre koşullu olarak kullanılıyorsa, bu, `Controlled` functor 'ı desteklemelidir; işlemin bir ters olması halinde, `Adjoint` functor desteği gerekir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-226">For example, if execution of the operation can be conditioned on the state of other qubits, it should support the `Controlled` functor; if the operation has an inverse, it should support the `Adjoint` functor.</span></span> <span data-ttu-id="1ba95-227">Funörler ve işlemler, [Q # ' daki işlemler ve işlevlerde](xref:microsoft.quantum.guide.operationsfunctions)ayrıntılı olarak ele alınmıştır, ancak burada bunun işlem imzasını nasıl değiştiren açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-227">Functors and operations are discussed in detail at [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions), but here we simply discuss how this alters the operation signature.</span></span>

<span data-ttu-id="1ba95-228">`Controlled`Bir işlem türünde ve/veya functor desteğinin gerekli olması için `Adjoint` , karşılık gelen özellikleri belirten bir ek açıklama eklememiz gerekir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-228">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="1ba95-229">Ek açıklama `is Ctl` (örn. `(Qubit => Unit is Ctl)` ), işlemin denetlenebilir olduğunu---, yani yürütmenin başka bir qubit veya qubits durumunda olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-229">An annotation `is Ctl` (e.g. `(Qubit => Unit is Ctl)`) indicates that the operation is controllable---that is, it's execution conditioned on the state of another qubit or qubits.</span></span> <span data-ttu-id="1ba95-230">Benzer şekilde, `is Adj` işlemin bir adjoint olduğunu veya yalnızca bir işlemi tamamen uygulayan ve bu durumda adjoint, durumu değişmeden bırakan bir "ters" olabilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-230">Similarly, `is Adj` indicates that the operation has an adjoint; or simply, it can be "inverted" such that successively applying an operation and then its adjoint to a state leaves the state unchanged.</span></span> 

<span data-ttu-id="1ba95-231">Bu tür bir işlemin hem hem de `Adjoint` `Controlled` functor desteklediğinden, bunu olarak ifade etmek istiyoruz `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-231">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="1ba95-232">Örneğin, yerleşik Pauli <xref:microsoft.quantum.intrinsic.x> işleminin türü vardır `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-232">For example, the built-in Pauli <xref:microsoft.quantum.intrinsic.x> operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span> 

<span data-ttu-id="1ba95-233">Herhangi bir belirtiyi desteklemeyen bir işlem türü, giriş ve çıkış türü ile tek başına, ek açıklama olmadan belirtilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-233">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>

### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="1ba95-234">Tür parametreli Işlevler ve Işlemler</span><span class="sxs-lookup"><span data-stu-id="1ba95-234">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="1ba95-235">Çağrılabilir türler tür parametreleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-235">Callable types may contain type parameters.</span></span>
<span data-ttu-id="1ba95-236">Tür parametreleri, tek bir teklifin önekli simgesiyle belirtilir; Örneğin, `'A` yasal bir tür parametresidir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-236">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>
<span data-ttu-id="1ba95-237">Türü tanımlama hakkında ayrıntılar-parametreli callables, [Q # sayfasındaki işlemler ve işlevler](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) için verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-237">Details on defining type-parameterized callables are provided on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) page.</span></span>

<span data-ttu-id="1ba95-238">Bir tür parametresi, tek bir imzada birden çok kez görünebilir.</span><span class="sxs-lookup"><span data-stu-id="1ba95-238">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="1ba95-239">Örneğin, bir dizinin her öğesine başka bir işlev uygulayan ve toplanan sonuçların geri döndürdüğü bir işlev imzaya sahip olur `(('A[], 'A->'A) -> 'A[])` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-239">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="1ba95-240">Benzer şekilde, iki işlemin birleşimini döndüren bir işlev imzaya sahip olabilir `((('A=>'B), ('B=>'C)) -> ('A=>'C))` .</span><span class="sxs-lookup"><span data-stu-id="1ba95-240">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="1ba95-241">Bir tür parametreli çağrılabilir çağrılırken, aynı tür parametresine sahip tüm bağımsız değişkenler aynı türde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="1ba95-241">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="1ba95-242">S #, bir tür parametresi için yerine gelebilecek olası türleri kısıtlayan bir mekanizma sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="1ba95-242">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

## <a name="whats-next"></a><span data-ttu-id="1ba95-243">Sırada Ne Var?</span><span class="sxs-lookup"><span data-stu-id="1ba95-243">What's Next?</span></span>
<span data-ttu-id="1ba95-244">Artık, Q # dilini oluşturan tüm türleri gördüğünüze göre, bu çeşitli türlerin ifadelerini oluşturma ve değiştirme hakkında bilgi almak için, [q # Içinde Ifade türüne](xref:microsoft.quantum.guide.expressions) gidebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="1ba95-244">Now that you've seen all the types which comprise the Q# language, you can head to [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) to see how to create and manipulate expressions of these various types.</span></span>


