---
title: 'S # veri türleri'
description: 'Yerleşik türler, diziler, tanımlama bilgileri, işlemler, işlevler ve Kullanıcı tanımlı türler dahil olmak üzere Q # programlama dilinde kullanılan farklı türler hakkında bilgi edinin.'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fc4c0b3fed9277c7f9f3ac421330df03c1b30e4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904664"
---
# <a name="the-type-model"></a><span data-ttu-id="3d7b6-103">Tür modeli</span><span class="sxs-lookup"><span data-stu-id="3d7b6-103">The Type Model</span></span>

<span data-ttu-id="3d7b6-104">Bu bölüm, Q # tür modelini düzenler ve türleri belirtmek ve bunlarla çalışmak için sözdizimini açıklar.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-104">This section lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>
<span data-ttu-id="3d7b6-105">Bu tür dikkatle kullanılması derleyicinin, derleme zamanında Q # programları hakkında güçlü garantiler sağlamasına yardımcı olabileceğini belirten, *kesin olarak yazılmış* bir dil olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-105">We note that Q# is a *strongly-typed* language, such that careful use of these types can help the compiler to provide strong guarantees about Q# programs at compile time.</span></span>

<span data-ttu-id="3d7b6-106">Mümkün olan en güçlü garantiyi sağlamak için, Q # içindeki türler arasındaki dönüştürmeler, bu dönüştürmeyi ifade eden işlevlere yapılan çağrılar kullanılarak açık olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-106">In order to provide the strongest guarantees possible, conversions between types in Q# must be explicit using calls to functions which express that conversion.</span></span> <span data-ttu-id="3d7b6-107"><xref:microsoft.quantum.convert> ad alanının bir parçası olarak çeşitli işlevler sağlanır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-107">A variety of such functions are provided as a part of the <xref:microsoft.quantum.convert> namespace.</span></span>
<span data-ttu-id="3d7b6-108">Diğer yandan uyumlu türlere yapılan yayınlar örtülü olarak gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-108">Upcasts to compatible types on the other hand happen implicitly.</span></span> 

<span data-ttu-id="3d7b6-109">Q #, doğrudan kullanılabilen basit türler ve diğer türlerden yeni türler oluşturmak için çeşitli yollar sağlar.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-109">Q# provides both primitive types, which can be used directly, and a variety of ways to produce new types from other types.</span></span>
<span data-ttu-id="3d7b6-110">Bu bölümün geri kalanında her birini açıklıyoruz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-110">We describe each in the rest of this section.</span></span>

## <a name="primitive-types"></a><span data-ttu-id="3d7b6-111">İlkel türler</span><span class="sxs-lookup"><span data-stu-id="3d7b6-111">Primitive Types</span></span>

<span data-ttu-id="3d7b6-112">Q # dili, diğer türlerin oluşturulabileceği çeşitli *temel türler*sağlar:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-112">The Q# language provides several *primitive types*, from which other types can be constructed:</span></span>

- <span data-ttu-id="3d7b6-113">`Int` türü, 64 bitlik işaretli bir tamsayıyı temsil eder, örneğin: `2`, `107`, `-5`.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-113">The `Int` type represents a 64-bit signed integer, e.g.: `2`, `107`, `-5`.</span></span>
- <span data-ttu-id="3d7b6-114">`BigInt` türü, rastgele boyutun işaretli bir tamsayı (örn. `2L`, `107L`, `-5L`) temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-114">The `BigInt` type represents a signed integer of arbitrary size, e.g. `2L`, `107L`, `-5L`.</span></span>
   <span data-ttu-id="3d7b6-115">Bu tür .NET <xref:System.Numerics.BigInteger> tabanlıdır</span><span class="sxs-lookup"><span data-stu-id="3d7b6-115">This type is based on the .NET <xref:System.Numerics.BigInteger></span></span>
   <span data-ttu-id="3d7b6-116">türüyle.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-116">type.</span></span>
- <span data-ttu-id="3d7b6-117">`Double` türü çift duyarlıklı kayan noktalı sayıyı temsil eder, örneğin: `0.0`, `-1.3`, `4e-7`.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-117">The `Double` type represents a double-precision floating-point number, e.g.: `0.0`, `-1.3`, `4e-7`.</span></span>
- <span data-ttu-id="3d7b6-118">`Bool` türü `true` veya `false`olabilen bir Boolean değeri temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-118">The `Bool` type represents a Boolean value which can either be `true` or `false`.</span></span>
- <span data-ttu-id="3d7b6-119">`Qubit` türü bir hisse bitini veya qubit 'i temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-119">The `Qubit` type represents a quantum bit or qubit.</span></span>
   <span data-ttu-id="3d7b6-120">`Qubit`s, kullanıcının opaktır; Bunlar ile mümkün olan tek işlem, başka bir işleme geçirilmekten farklı kimlik (eşitlik) için test amaçlıdır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-120">`Qubit`s are opaque to the user; the only operation possible with them, other than passing them to another operation, is to test for identity (equality).</span></span>
   <span data-ttu-id="3d7b6-121">Sonuç olarak, `Qubit`s üzerindeki eylemler bir hisse işlemcisi (veya bir simülasyonu) üzerinde iç yönergeler çağırarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-121">Ultimately, actions on `Qubit`s are implemented by calling intrinsic instructions on a quantum processor (or a simulation thereof).</span></span>
- <span data-ttu-id="3d7b6-122">`Pauli` türü, dört adet tek qubit Pauli işleçlerinden birini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-122">The `Pauli` type represents one of the four single-qubit Pauli operators.</span></span>
   <span data-ttu-id="3d7b6-123">Bu tür, döndürmeler için temel işlemi göstermek ve ölçülecek observable 'ı belirtmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-123">This type is used to denote the base operation for rotations and to specify the observable being measured.</span></span>
   <span data-ttu-id="3d7b6-124">Bu, dört olası değeri olan numaralandırılmış bir türdür: `PauliI`, `PauliX`, `PauliY`ve `PauliZ`, `Pauli`türünde sabitler.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-124">This is an enumerated type that has four possible values: `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, which are constants of type `Pauli`.</span></span>
- <span data-ttu-id="3d7b6-125">`Result` türü bir ölçünün sonucunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-125">The `Result` type represents the result of a measurement.</span></span>
   <span data-ttu-id="3d7b6-126">Bu, iki olası değeri olan numaralandırılmış bir türdür: `One` ve `Zero`, `Result`türünde sabitler.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-126">This is an enumerated type with two possible values: `One` and `Zero`, which are constants of type `Result`.</span></span>
   <span data-ttu-id="3d7b6-127">`Zero` + 1 eigenvalue değerinin ölçüldüğünü belirtir; `One`-1 eigenvalue değerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-127">`Zero` indicates that the +1 eigenvalue was measured; `One` indicates the -1 eigenvalue.</span></span>
- <span data-ttu-id="3d7b6-128">`Range` türü, `start..step..stop`tarafından belirtilen ve adım seçeneklerini gösteren bir tamsayılar dizisini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-128">The `Range` type represents a sequence of integers, denoted by `start..step..stop`, where denoting the step is options.</span></span> 
   <span data-ttu-id="3d7b6-129">Bu `start .. stop` `start..1..stop`karşılık gelir ve örn. `1..2..7` $\{1, 3, 5, 7\}$ dizisini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-129">That is `start .. stop` corresponds to `start..1..stop`, and e.g. `1..2..7` represents the sequence $\{1, 3, 5, 7\}$.</span></span>
- <span data-ttu-id="3d7b6-130">`String` türü, bir kez oluşturulduktan sonra kullanıcıya donuk olan Unicode karakterlerinden oluşan bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-130">The `String` type is a sequence of Unicode characters that is opaque to the user once created.</span></span>
  <span data-ttu-id="3d7b6-131">Bu tür, bir hata veya tanılama olayı durumunda iletileri klasik bir konağa raporlamak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-131">This type is used to report messages to a classical host in the case of an error or diagnostic event.</span></span>
- <span data-ttu-id="3d7b6-132">`Unit` türü yalnızca bir değer `()`izin veren türdür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-132">The `Unit` type is the type that allows only one value `()`.</span></span> 
  <span data-ttu-id="3d7b6-133">Bu tür, Q # işlevinin veya işleminin hiçbir bilgi döndürdüğünü göstermek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-133">This type is used to indicate that Q# function or operation returns no information.</span></span> 

<span data-ttu-id="3d7b6-134">`true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`ve `Zero` sabitleri, Q # içindeki tüm ayrılmış sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-134">The constants `true`, `false`, `PauliI`, `PauliX`, `PauliY`, `PauliZ`, `One`, and `Zero` are all reserved symbols in Q#.</span></span>

## <a name="array-types"></a><span data-ttu-id="3d7b6-135">Dizi türleri</span><span class="sxs-lookup"><span data-stu-id="3d7b6-135">Array Types</span></span>

<span data-ttu-id="3d7b6-136">Geçerli bir Q # tür `'T`verildiğinde, `'T`türünde bir değer dizisini temsil eden bir tür vardır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-136">Given any valid Q# type `'T`, there is a type that represents an array of values of type `'T`.</span></span>
<span data-ttu-id="3d7b6-137">Bu dizi türü `'T[]`olarak temsil edilir; Örneğin, `Qubit[]` veya `Int[][]`.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-137">This array type is represented as `'T[]`; for example, `Qubit[]` or `Int[][]`.</span></span>
<span data-ttu-id="3d7b6-138">Örneğin, bir tamsayılar koleksiyonu `Int[]`gösterilir, ancak `(Bool, Pauli)` değerlerinin dizi dizileri `(Bool, Pauli)[][]`olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-138">For instance, a collection of integers is denoted `Int[]`, while an array of arrays of `(Bool, Pauli)` values is denoted `(Bool, Pauli)[][]`.</span></span>

<span data-ttu-id="3d7b6-139">İkinci örnekte bunun, dikdörtgen iki boyutlu bir dizi değil, potansiyel olarak pürüzlü dizi dizileri temsil ettiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-139">In the second example, note that this represents a potentially jagged array of arrays, and not a rectangular two-dimensional array.</span></span>
<span data-ttu-id="3d7b6-140">Q #, dikdörtgen çok boyutlu diziler için destek sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-140">Q# does not provide support for rectangular multi-dimensional arrays.</span></span>

<span data-ttu-id="3d7b6-141">Dizi değeri, `[PauliI, PauliX, PauliY, PauliZ]`içinde olduğu gibi, bir dizinin öğeleri etrafında köşeli ayraçlar kullanılarak Q # kaynak kodunda yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-141">An array value can be written in Q# source code by using square brackets around the elements of an array, as in `[PauliI, PauliX, PauliY, PauliZ]`.</span></span>
<span data-ttu-id="3d7b6-142">Dizi sabit değerinin türü dizideki tüm öğelerin ortak temel türüne göre belirlenir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-142">The type of an array literal is determined by the common base type of all items in the array.</span></span> 

> [!WARNING]
> <span data-ttu-id="3d7b6-143">Dizinin öğeleri, dizi oluşturulduktan sonra değiştirilemez.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-143">The elements of an array cannot be changed after the array has been created.</span></span>
> <span data-ttu-id="3d7b6-144">Güncelleştirme ve yeniden atama deyimleri ve/veya kopyalama ve güncelleştirme ifadeleri, değiştirilmiş bir diziyi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-144">Update-and-reassign statements and/or copy-and-update expressions can be used to construct a modified array.</span></span>

<span data-ttu-id="3d7b6-145">Alternatif olarak, bir dizi `new` anahtar sözcüğü kullanılarak boyutundan oluşturulabilir:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-145">Alternatively, an array can be created from its size using the `new` keyword:</span></span>

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

<span data-ttu-id="3d7b6-146">Her iki durumda da, bir dizi oluşturulduktan sonra `Length` çekirdek işlevi, öğe sayısını `Int`olarak elde etmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-146">In either case, once an array has been constructed, the core function `Length` can be used to obtain the number of elements as an `Int`.</span></span>
<span data-ttu-id="3d7b6-147">Diziler, bir dizinin öğelerinin bir alt kümesini içeren tek öğe veya yeni diziler elde etmek için tür `Int` ya da `Range`tür olan alt simgeler ile köşeli ayraç kullanılarak alt simge olabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-147">Arrays can be subscripted using square brackets, with subscripts either having type `Int` or type `Range`, to obtain either single elements or new arrays containing a subset of the elements of an array.</span></span>
<span data-ttu-id="3d7b6-148">Dizilerin alt simgeleri sıfır tabanlıdır:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-148">The subscripts of arrays are zero-based:</span></span>

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a><span data-ttu-id="3d7b6-149">Demet türleri</span><span class="sxs-lookup"><span data-stu-id="3d7b6-149">Tuple Types</span></span>

<span data-ttu-id="3d7b6-150">Sıfır veya daha fazla farklı tür `T0`, `T1`,... `Tn`, yeni bir *tanımlama grubu türünü* `(T0, T1, ..., Tn)`olarak gösteremez.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-150">Given zero or more different types `T0`, `T1`, ..., `Tn`, we can denote a new  *tuple type* as `(T0, T1, ..., Tn)`.</span></span>
<span data-ttu-id="3d7b6-151">Yeni bir demet türü oluşturmak için kullanılan türler, `(Int, (Qubit, Qubit))`gibi kendi tanımlama grupları olabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-151">The types used to construct a new tuple type can themselves be tuples, as in `(Int, (Qubit, Qubit))`.</span></span>
<span data-ttu-id="3d7b6-152">Bu iç içe geçme her zaman sınırlıdır, ancak demet türleri hiçbir koşulda kendilerini içeremez.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-152">Such nesting is always finite, however, as tuple types cannot under any circumstances contain themselves.</span></span>

<span data-ttu-id="3d7b6-153">Yeni demet türünün değerleri, kayıt düzeni içindeki her türden değer dizileri tarafından oluşturulan dizileridir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-153">Values of the new tuple type are tuples formed by sequences of values from each type in the tuple.</span></span>
<span data-ttu-id="3d7b6-154">Örneğin, `(3, false)` türü `(Int, Bool)`demet türü olan bir kayıt türüdür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-154">For instance, `(3, false)` is a tuple whose type is the tuple type `(Int, Bool)`.</span></span>
<span data-ttu-id="3d7b6-155">Tanımlama dizileri, dizi dizilerindeki diziler, alt tanımlama grupları, vb. öğeleri oluşturmak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-155">It is possible to create arrays of tuples, tuples of arrays, tuples of sub-tuples, etc.</span></span>

<span data-ttu-id="3d7b6-156">Q # 0,3 itibariyle `Unit`, boş tanımlama grubunun *türünün* adıdır; `()`, boş demet *değeri*için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-156">As of Q# 0.3, `Unit` is the name of the *type* of the empty tuple; `()` is used for the empty tuple *value*.</span></span>

<span data-ttu-id="3d7b6-157">Demet örnekleri sabittir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-157">Tuple instances are immutable.</span></span>
<span data-ttu-id="3d7b6-158">S #, oluşturulduktan sonra bir kayıt düzeninin içeriğini değiştirme mekanizması sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-158">Q# does not provide a mechanism to change the contents of a tuple once created.</span></span>

<span data-ttu-id="3d7b6-159">Tanımlama grupları, her bir değer toplamak için Q # boyunca kullanılan güçlü bir kavramdır; bu da, daha kolay bir şekilde geçiş yapmayı kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-159">Tuples are a powerful concept used throughout Q# to collect values together into a single value, making it easier to pass them around.</span></span>
<span data-ttu-id="3d7b6-160">Özellikle, tanımlama grubu gösterimini kullanarak her işlemin ve çağrılabilir şekilde tam olarak bir giriş aldığını ve tam olarak bir çıkış döndürdüğünü ifade edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-160">In particular, using tuple notation, we can express that every operation and callable takes exactly one input and returns exactly one output.</span></span>

### <a name="singleton-tuple-equivalence"></a><span data-ttu-id="3d7b6-161">Tek kayıt düzeni denklik</span><span class="sxs-lookup"><span data-stu-id="3d7b6-161">Singleton Tuple Equivalence</span></span>

<span data-ttu-id="3d7b6-162">`('T1)`, `(5)` veya `([1,2,3])`gibi tek öğeli bir tanımlama grubu oluşturmak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-162">It is possible to create a singleton (single-element) tuple, `('T1)`, such as `(5)` or `([1,2,3])`.</span></span>
<span data-ttu-id="3d7b6-163">Ancak, Q #, tek bir kayıt kümesini, iliştirilmiş türdeki bir değere tamamen eşdeğer olarak değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-163">However, Q# treats a singleton tuple as completely equivalent to a value of the enclosed type.</span></span>
<span data-ttu-id="3d7b6-164">Diğer bir deyişle, `5` ile `(5)`arasında veya `5` ile `(((5)))`arasında ya da `(5, (6))` ile `(5, 6)`arasında bir fark yoktur.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-164">That is, there is no difference between `5` and `(5)`, or between `5` and `(((5)))`, or between `(5, (6))` and `(5, 6)`.</span></span>

<span data-ttu-id="3d7b6-165">Bu denklik, atama ve ifadeler dahil tüm amaçlar için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-165">This equivalence applies for all purposes, including assignment and expressions.</span></span>
<span data-ttu-id="3d7b6-166">`5+3`yazmak için `(5)+3` yazmak için geçerli olduğu gibi, her iki ifade de `8`olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-166">It is just as valid to write `(5)+3` as to write `5+3`, and both expressions will evaluate to `8`.</span></span>
<span data-ttu-id="3d7b6-167">Özellikle, bu, giriş kümesi veya çıkış grubu türü olan bir işlemin veya işlevin tek bir bağımsız değişken alan veya tek bir değer döndüren bir alana sahip olabileceği anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-167">In particular, this means that an operation or function whose input tuple or output tuple type has one field can be thought of as taking a single argument or returning a single value.</span></span>

<span data-ttu-id="3d7b6-168">Bu özelliğe, _tek demet denklik_olarak başvurduk.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-168">We refer to this property as _singleton tuple equivalence_.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="3d7b6-169">Kullanıcı tanımlı türler</span><span class="sxs-lookup"><span data-stu-id="3d7b6-169">User-Defined Types</span></span>

<span data-ttu-id="3d7b6-170">Bir Q # dosyası, geçerli bir türden tek bir değer içeren yeni bir adlandırılmış tür tanımlayabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-170">A Q# file may define a new named type containing a single value of any legal type.</span></span>
<span data-ttu-id="3d7b6-171">`T`tanımlama grubu türü için, `newtype` ifadesiyle `T` alt türü olan yeni bir Kullanıcı tanımlı tür bildirebiliriz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-171">For any tuple type `T`, we can declare a new user-defined type that is a subtype of `T` with the `newtype` statement.</span></span>
<span data-ttu-id="3d7b6-172">@"microsoft.quantum.math" ad alanında, örneğin, karmaşık sayılar Kullanıcı tanımlı bir tür olarak tanımlanmıştır:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-172">In the @"microsoft.quantum.math" namespace, for instance, complex numbers are defined as a user-defined type:</span></span>

```qsharp
newtype Complex = (Double, Double);
```

<span data-ttu-id="3d7b6-173">Bu ifade `Double`türünde iki anonim öğe içeren yeni bir tür oluşturur.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-173">This statement creates a new type with two anonymous items of type `Double`.</span></span>   
<span data-ttu-id="3d7b6-174">Anonim öğelerden biri dışında, Kullanıcı tanımlı türler de Q # sürüm 0,7 veya üzeri olarak adlandırılmış öğeleri destekler.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-174">Aside from anonymous items, user defined types also support named items as of Q# version 0.7 or higher.</span></span> <span data-ttu-id="3d7b6-175">Örneğin, bir karmaşık sayının gerçek parçasını temsil eden Double için `Re` ve sanal bölüm için `Im` olarak adlandırdık:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-175">For example, we could have named the to items `Re` for the double representing the real part of a complex number and `Im` for the imaginary part:</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="3d7b6-176">Kullanıcı tanımlı tür içindeki bir öğenin adlandırılması, tüm öğelerin adlandırılması gerektiğini göstermez; adlandırılmış ve adlandırılmamış öğelerin herhangi bir birleşimi desteklenir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-176">Naming one item in a user defined type does not imply that all items need to be named - any combination of named and unnamed items is supported.</span></span> <span data-ttu-id="3d7b6-177">Ayrıca, iç öğeler de adlandırılmış olabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-177">Furthermore, also inner items may be named.</span></span>
<span data-ttu-id="3d7b6-178">Aşağıda tanımlanan `Nested` türü, temel alınan bir tür `(Double, (Int, String))`vardır ve yalnızca `Int` türü öğe ve diğer tüm öğeler anonimdir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-178">The type `Nested` as defined below for example has an underlying type `(Double, (Int, String))`, of which only the item of type `Int` is named and all other items are anonymous.</span></span> 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
<span data-ttu-id="3d7b6-179">Adlandırılmış öğeler, erişim operatörü `::`aracılığıyla doğrudan erişilebilecekleri avantajına sahiptir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-179">Named items have the advantage that they can be accessed directly via the access operator `::`.</span></span> 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

<span data-ttu-id="3d7b6-180">Diğer yandan anonim öğelere erişmek için, sarmalanmış değerin ilk olarak `!`sonek işleci kullanılarak ayıklanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-180">In order to access anonymous items on the other hand, the wrapped value first needs to be extracted using the postfix operator `!`.</span></span>
<span data-ttu-id="3d7b6-181">`!`, bir Kullanıcı tanımlı türde bulunan değeri ayıklamaya izin veren "Unwrap" işleci.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-181">The "unwrap" operator, `!`, allows to extract the value contained in a user defined type.</span></span>
<span data-ttu-id="3d7b6-182">Böyle bir "sarmalama" ifadesinin türü, Kullanıcı tanımlı türün temel türüdür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-182">The type of such an "unwrap" expression is the underlying type of the user defined type.</span></span> 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

<span data-ttu-id="3d7b6-183">Unwrap işleci, tam olarak bir sarmalama katmanını sarmalanmış olarak kaldırır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-183">The unwrap operator unwraps exactly one layer of wrapping.</span></span>
<span data-ttu-id="3d7b6-184">Çarpma sarmalanmış bir değere erişmek için birden çok sarmalama işleci kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-184">Multiple unwrap operators may be used to access a multiply-wrapped value.</span></span>

<span data-ttu-id="3d7b6-185">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-185">For instance:</span></span>

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

<span data-ttu-id="3d7b6-186">Daha fazla ayrıntı için [sarmalama ifadelerinin](xref:microsoft.quantum.language.expressions#unwrap-expressions) ve [operatör önceliğinde](xref:microsoft.quantum.language.expressions#operator-precedence) bölüme göz atın.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-186">Take a look at the section on [unwrap expressions](xref:microsoft.quantum.language.expressions#unwrap-expressions) and [operators precedence](xref:microsoft.quantum.language.expressions#operator-precedence) for more details.</span></span>

<span data-ttu-id="3d7b6-187">Kullanıcı tanımlı türün değerleri, karşılık gelen tür Oluşturucusu çağırarak oluşturulabilir:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-187">Values of a user defined type can be created by calling the corresponding type constructor:</span></span>

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

<span data-ttu-id="3d7b6-188">Alternatif olarak, [kopyalama ve güncelleştirme ifadeleri](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)kullanılarak mevcut olanlardan yeni değerler oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-188">Alternatively, new values can be created from existing ones using [copy-and-update expressions](xref:microsoft.quantum.language.expressions#copy-and-update-expressions).</span></span> <span data-ttu-id="3d7b6-189">Diziler gibi ifadeler, özgün ifadenin tüm öğe değerlerini, belirtilen adlandırılmış öğelerin özel durumuyla birlikte kopyalar.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-189">Like for arrays, such expressions copy all item values of the original expression, with the exception of the specified named items.</span></span> <span data-ttu-id="3d7b6-190">Bu değerler için, ifadenin sağ tarafında tanımlananlara ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-190">For these the values are set to the ones defined on the right hand side of the expression.</span></span> <span data-ttu-id="3d7b6-191">Aynı zamanda Kullanıcı tanımlı türlerde adlandırılmış öğeler için kullanılabilen, örneğin [Update-ve-yeniden atama deyimleri](xref:microsoft.quantum.language.statements#update-and-reassign-statement)gibi diğer dil yapıları de mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-191">Any other language constructs, like for example [update-and-reassign statements](xref:microsoft.quantum.language.statements#update-and-reassign-statement), that are available for array items exist for named-items in user defined types as well.</span></span>

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

<span data-ttu-id="3d7b6-192">Kullanıcı tanımlı türler, diğer herhangi bir tür kullanılabilir her yerde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-192">User-defined types may be used anywhere any other type may be used.</span></span>
<span data-ttu-id="3d7b6-193">Özellikle, Kullanıcı tanımlı bir türün dizisini tanımlamak ve Kullanıcı tanımlı bir türü bir demet türünün öğesi olarak eklemek mümkündür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-193">In particular, it is possible to define an array of a user-defined type and to include a user-defined type as an element of a tuple type.</span></span>

<span data-ttu-id="3d7b6-194">Özyinelemeli tür yapıları oluşturmak mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-194">It is not possible to create recursive type structures.</span></span>
<span data-ttu-id="3d7b6-195">Diğer bir deyişle, Kullanıcı tanımlı bir türü tanımlayan tür, Kullanıcı tanımlı türdeki bir öğe içeren bir demet türü olamaz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-195">That is, the type that defines a user-defined type may not be a tuple type that includes an element of the user-defined type.</span></span>
<span data-ttu-id="3d7b6-196">Daha genel olarak, Kullanıcı tanımlı türlerin birbirlerine döngüsel bağımlılıkları olmayabilir, bu nedenle aşağıdaki tür tanımları kümesi geçersizdir:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-196">More generally, user-defined types may not have cyclic dependencies on each other, so the following set of type definitions would be illegal:</span></span>

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

<span data-ttu-id="3d7b6-197">Karmaşık tanımlama grubu türleri için kısa diğer adlar sağlamaya ek olarak, bu tür türler tanımlamanın önemli bir avantajı, belirli bir değerin amacını belgelememelerdir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-197">In addition to providing short aliases for potentially complicated tuple types, one significant advantage of defining such types is that they can document the intent of a particular value.</span></span>
<span data-ttu-id="3d7b6-198">`Complex`örneğine dönerek, bir Kullanıcı tanımlı tür olarak 2B kutupsal koordinatları de tanımlanabilir:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-198">Returning to the example of `Complex`, one could have also defined 2D polar coordinates as a user-defined type:</span></span>

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

<span data-ttu-id="3d7b6-199">Hem `Complex` hem de `Polar` hem temel alınan bir tür `(Double, Double)`olsa da, iki tür de her ikisi de, her ikisi de aynı şekilde, bir karmaşık matematik işlevini kutupsal koordinatlarla çağırma riskini en aza indirir ve tam tersi de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-199">Even though both `Complex` and `Polar` are both have an underlying type `(Double, Double)`, the two types are wholly incompatible in Q#, minimizing the risk of accidentally calling a complex math function with polar coordinates and vice versa.</span></span>
<span data-ttu-id="3d7b6-200">Bu şekilde, Kullanıcı tanımlı türlerin, örneğin kayıtları F# olarak benzer bir rolü vardır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-200">In this way, user-defined types have a similar role as Records in F# for example.</span></span> 


## <a name="operation-and-function-types"></a><span data-ttu-id="3d7b6-201">İşlem ve Işlev türleri</span><span class="sxs-lookup"><span data-stu-id="3d7b6-201">Operation and Function Types</span></span>

<span data-ttu-id="3d7b6-202">Bir Q # _işlemi_ bir hisse alt yordamı.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-202">A Q# _operation_ is a quantum subroutine.</span></span>
<span data-ttu-id="3d7b6-203">Başka bir deyişle kuantum işlemlerini içeren çağrılabilir bir yordamdır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-203">That is, it is a callable routine that contains quantum operations.</span></span>

<span data-ttu-id="3d7b6-204">Bir Q # _işlevi_ , bir hisse algoritması içinde kullanılan klasik bir alt yordam.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-204">A Q# _function_ is a classical subroutine used within a quantum algorithm.</span></span>
<span data-ttu-id="3d7b6-205">Klasik kod içerebilir, ancak hisse işlem işlemleri yoktur.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-205">It may contain classical code but no quantum operations.</span></span>
<span data-ttu-id="3d7b6-206">Özellikle, işlevler qubit ayıramayabilir veya bu işlemleri çağırabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-206">Specifically, functions may not allocate or borrow qubits, nor may they call operations.</span></span>
<span data-ttu-id="3d7b6-207">Bununla birlikte, işlemleri veya işleme için qubits 'i geçirmek mümkündür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-207">It is possible, however, to pass them operations or qubits for processing.</span></span>
<span data-ttu-id="3d7b6-208">Bu nedenle işlevler, aynı bağımsız değişkenlerle çağrı yapan her zaman aynı sonucu üreten anlamda tamamen belirleyici olur.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-208">Functions are thus entirely deterministic in the sense that calling them with the same arguments will always produce the same result.</span></span> 

<span data-ttu-id="3d7b6-209">Birlikte, işlemler ve işlevler _callables_olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-209">Together, operations and functions are called _callables_.</span></span>  <span data-ttu-id="3d7b6-210">Aşağıda bunların bazı [örneklerini](#examples) görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-210">You can see some [examples](#examples) of these below.</span></span>

<span data-ttu-id="3d7b6-211">Tüm Q # callables, giriş olarak tek bir değer alıp çıkış olarak tek bir değer döndürecek şekilde değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-211">All Q# callables are considered to take a single value as input and return a single value as output.</span></span>
<span data-ttu-id="3d7b6-212">Hem giriş hem de çıkış değerleri tanımlama grupları olabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-212">Both the input and output values may be tuples.</span></span>
<span data-ttu-id="3d7b6-213">Sonuç döndüren `Unit`callables.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-213">Callables that have no result return `Unit`.</span></span>
<span data-ttu-id="3d7b6-214">Girişi olmayan callables, boş kayıt grubunu giriş olarak alır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-214">Callables that have no input take the empty tuple as input.</span></span>

<span data-ttu-id="3d7b6-215">Çağrılabilir için temel tür, hem `'Tinput` hem de `'Tresult` türler olan `('Tinput => 'Tresult)` veya `('Tinput -> 'Tresult)`olarak yazılır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-215">The basic type for any callable is written as `('Tinput => 'Tresult)` or `('Tinput -> 'Tresult)`, where both `'Tinput` and `'Tresult` are types.</span></span>
<span data-ttu-id="3d7b6-216">`=>`olan ilk form, işlemler için kullanılır; ikinci form, işlevleri için `->`.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-216">The first form, with `=>`, is used for operations; the second form, with `->`, for functions.</span></span>
<span data-ttu-id="3d7b6-217">Örneğin `((Qubit, Pauli) => Result)`, olası bir tek qubit ölçüm işleminin imzasını temsil eder.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-217">For example, `((Qubit, Pauli) => Result)` represents the signature for a possible single-qubit measurement operation.</span></span>

<span data-ttu-id="3d7b6-218">İşlev türleri kendi imzasıyla tamamen belirtilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-218">Function types are completely specified by their signature.</span></span>
<span data-ttu-id="3d7b6-219">Örneğin, bir açının sinüsünü hesaplayan bir işlevin türü `(Double -> Double)`olacaktır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-219">For example, a function that computes the sine of an angle would have type `(Double -> Double)`.</span></span>

<span data-ttu-id="3d7b6-220">İşlemler (ancak işlevleri değil), işlem türünün bir parçası olarak ifade edilen bazı ek _özelliklere_ sahiptir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-220">Operations—but not functions—have certain additional _characteristics_ that are expressed as part of the operation type.</span></span> <span data-ttu-id="3d7b6-221">Bu tür özellikler, işlemin desteklediği komik ilgili bilgileri içerir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-221">Such characteristics include information about what functors the operation supports.</span></span>
<span data-ttu-id="3d7b6-222">Funörler, temel bir işlemin bir özelleştirmesi üreten meta işlemlerdir; Aşağıdaki bkz. [Funörler](#functors).</span><span class="sxs-lookup"><span data-stu-id="3d7b6-222">Functors are meta-operations that generate a specialization of a base operation; see [Functors](#functors), below.</span></span>

<span data-ttu-id="3d7b6-223">İşlem türleri, giriş türü, çıkış türü ve özellikleri tarafından belirtilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-223">Operation types are specified by the their input type, output type, and their characteristics.</span></span>    
<span data-ttu-id="3d7b6-224">Bir işlem türünde `Controlled` ve/veya `Adjoint` functor desteğinin gerekli olması için, karşılık gelen özellikleri belirten bir ek açıklama eklememiz gerekir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-224">In order to require support for the `Controlled` and/or `Adjoint` functor in an operation type, we need to add an annotation indicating the corresponding characteristics.</span></span>
<span data-ttu-id="3d7b6-225">Örneğin bir ek açıklama `is Ctl`, işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-225">An annotation `is Ctl` for example indicates that the operation is controllable.</span></span> <span data-ttu-id="3d7b6-226">Bu tür bir işlemin hem `Adjoint` hem de `Controlled` functor desteklemesini istiyorsanız bunu `(Qubit => Unit is Adj + Ctl)`olarak ifade edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-226">If we want to require that an operation of that type supports both the `Adjoint` and `Controlled` functor we can express this as `(Qubit => Unit is Adj + Ctl)`.</span></span> <span data-ttu-id="3d7b6-227">Kullanılan işlem özellikleri `Adj` ve `Ctl` kesinlikle konuşurken, her etiketin, örneğin belirli bir functor desteği gibi belirli bir işlem özelliklerini gösterdiği, önceden tanımlanmış iki etiket kümesi vardır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-227">The used operation characteristics `Adj` and `Ctl` strictly speaking are two pre-defined sets of labels, where each label indicates a particular operation characteristics like e.g. support for a particular functor.</span></span>
<span data-ttu-id="3d7b6-228">Bu nedenle `+`, bu iki kümenin birleşimini belirtmek için kullanılır ve `*` kesişimini belirtmek için kullanılır. her iki küme için de ortak olan Etiketler.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-228">Hence, `+` is used to indicate the union of those two sets, and `*` is used to indicate the intersection - i.e. the labels that are common to both sets.</span></span>  

<span data-ttu-id="3d7b6-229">Örneğin, Pauli `X` işleminin türü `(Qubit => Unit is Adj + Ctl)`vardır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-229">For example, the Pauli `X` operation has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3d7b6-230">Herhangi bir belirtiyi desteklemeyen bir işlem türü, giriş ve çıkış türü ile tek başına, ek açıklama olmadan belirtilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-230">An operation type that does not support any functors is specified by its input and output type alone, with no additional annotation.</span></span>


### <a name="type-parameterized-functions-and-operations"></a><span data-ttu-id="3d7b6-231">Tür parametreli Işlevler ve Işlemler</span><span class="sxs-lookup"><span data-stu-id="3d7b6-231">Type-Parameterized Functions and Operations</span></span>

<span data-ttu-id="3d7b6-232">Çağrılabilir türler tür parametreleri içerebilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-232">Callable types may contain type parameters.</span></span>
<span data-ttu-id="3d7b6-233">Tür parametreleri, tek bir teklifin önekli simgesiyle belirtilir; Örneğin, `'A` yasal bir tür parametresidir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-233">Type parameters are indicated by a symbol prefixed by a single quote; for example, `'A` is a legal type parameter.</span></span>

<span data-ttu-id="3d7b6-234">Bir tür parametresi, tek bir imzada birden çok kez görünebilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-234">A type parameter may appear more than once in a single signature.</span></span>
<span data-ttu-id="3d7b6-235">Örneğin, bir dizinin her öğesine başka bir işlev uygulayan ve toplanan sonuçların döndüren bir işlev imza `(('A[], 'A->'A) -> 'A[])`olacaktır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-235">For example, a function that applies another function to each element of an array and returns the collected results would have signature `(('A[], 'A->'A) -> 'A[])`.</span></span>
<span data-ttu-id="3d7b6-236">Benzer şekilde, iki işlemin birleşimini döndüren bir işlev imzaya `((('A=>'B), ('B=>'C)) -> ('A=>'C))`sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-236">Similarly, a function that returns the composition of two operations might have signature `((('A=>'B), ('B=>'C)) -> ('A=>'C))`.</span></span>

<span data-ttu-id="3d7b6-237">Bir tür parametreli çağrılabilir çağrılırken, aynı tür parametresine sahip tüm bağımsız değişkenler aynı türde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-237">When invoking a type-parameterized callable, all arguments that have the same type parameter must be of the same type.</span></span>

<span data-ttu-id="3d7b6-238">S #, bir tür parametresi için yerine gelebilecek olası türleri kısıtlayan bir mekanizma sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-238">Q# does not provide a mechanism for constraining the possible types that might be substituted for a type parameter.</span></span>

### <a name="type-compatibility"></a><span data-ttu-id="3d7b6-239">Tür uyumluluğu</span><span class="sxs-lookup"><span data-stu-id="3d7b6-239">Type Compatibility</span></span>

<span data-ttu-id="3d7b6-240">Desteklenen ek bir işlem, daha az komik olan bir işlemin her yerde kullanılabilir, ancak aynı imza beklenmektedir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-240">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="3d7b6-241">Örneğin, `(Qubit => Unit is Adj)` türünde bir işlem, `(Qubit => Unit)` türünde bir işlemin beklendiği her yerde kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-241">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="3d7b6-242">Q #, çağrılabilir dönüş türlerine göre değişkenle birlikte bulunur: `'A` bir türü döndüren çağrılabilir, aynı giriş türüne ve `'A` uyumlu olan bir sonuç türüne sahip çağrılabilir ile uyumludur.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-242">Q# is covariant with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="3d7b6-243">S #, giriş türlerine göre değişken karşıtı: giriş, aynı sonuç türü ve `'A`ile uyumlu bir giriş türü olan çağrılabilir ile uyumlu olduğundan `'A` bir türü alan çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-243">Q# is contravariant with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="3d7b6-244">Diğer bir deyişle, aşağıdaki tanımlar verilir:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-244">That is, given the following definitions:</span></span>

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

<span data-ttu-id="3d7b6-245">aşağıdakiler doğrudur:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-245">the following are true:</span></span>

- <span data-ttu-id="3d7b6-246">`ConjugateInvertWith` işlevi, `Invert` veya `ApplyUnitary``inner` bağımsız değişkeniyle çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-246">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="3d7b6-247">İşlev `ConjugateUnitaryWith`, `ApplyUnitary``inner` bağımsız değişkeniyle çağrılabilir, ancak `Invert`.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-247">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="3d7b6-248">`(Qubit[] => Unit is Adj + Ctl)` türünde bir değer `ConjugateInvertWith`döndürebilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-248">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3d7b6-249">Q # 0,3, Kullanıcı tanımlı türlerin davranışında önemli bir farklılık sunar.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-249">Q# 0.3 introduces a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="3d7b6-250">Kullanıcı tanımlı türler, alt tür yerine temel alınan türün Sarmalanan bir sürümü olarak değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-250">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="3d7b6-251">Bu, Kullanıcı tanımlı türün bir değerinin, temel alınan türden bir değerin beklenildiği durumlarda kullanılamaz olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-251">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>

### <a name="functors"></a><span data-ttu-id="3d7b6-252">Functorları</span><span class="sxs-lookup"><span data-stu-id="3d7b6-252">Functors</span></span>

<span data-ttu-id="3d7b6-253">Q # ' daki bir functor, başka bir işlemden yeni bir işlem tanımlayan bir fabrikadır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-253">A functor in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="3d7b6-254">Funörler, yeni işlemin uygulamasını tanımlarken temel işlemin uygulamasına erişebilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-254">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="3d7b6-255">Bu nedenle, funörler geleneksel daha yüksek düzey işlevlerden daha karmaşık işlevler gerçekleştirebilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-255">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span>

<span data-ttu-id="3d7b6-256">Funörler, Q # tür sisteminde bir gösterimine sahip değildir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-256">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="3d7b6-257">Bu nedenle, şu anda bunları bir değişkene bağlamak veya bağımsız değişken olarak geçirmek mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-257">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="3d7b6-258">Komik bir ctor, bir işleme uygulanarak yeni bir işlem döndürerek kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-258">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="3d7b6-259">Örneğin, `Adjoint` functor `Y` işlemine uygulamanın sonucu olan işlem `Adjoint Y`olarak yazılmıştır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-259">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="3d7b6-260">Yeni işlem daha sonra başka bir işlem gibi çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-260">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="3d7b6-261">Bu nedenle, `Adjoint Y(q1)` yeni bir işlem oluşturmak için adjoint functor `Y` işlemine uygular ve bu yeni işlemi `q1`uygular.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-261">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>

<span data-ttu-id="3d7b6-262">Benzer şekilde, `Controlled X(controls, target)` yeni bir işlem oluşturmak için denetlenen functor `X` işlemine uygular ve bu yeni işlemi `controls` ve `target`uygular.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-262">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

<span data-ttu-id="3d7b6-263">Q # içindeki iki standart komik `Adjoint` ve `Controlled`.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-263">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

#### <a name="adjoint"></a><span data-ttu-id="3d7b6-264">Adjoint</span><span class="sxs-lookup"><span data-stu-id="3d7b6-264">Adjoint</span></span>

<span data-ttu-id="3d7b6-265">Hisse bilgi işlem ortamında, bir işlemin adjoint işlemi, işlemin karmaşık eşleniği olarak devrik bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-265">In quantum computing, the adjoint of an operation is the complex conjugate transpose of the operation.</span></span>
<span data-ttu-id="3d7b6-266">Bir Unitary işleci uygulayan işlemler için, adjoint işlemin tersidir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-266">For operations that implement a unitary operator, the adjoint is the inverse of the operation.</span></span>
<span data-ttu-id="3d7b6-267">Bir qubits kümesi üzerinde diğer Unitary işlemlerini bir dizi olarak çağıran basit bir işlem için, bu, ters sırada alt işlemlerin aynı qubits 'ler üzerinde bir arada uygulanarak, adjoint hesaplanmayabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-267">For a simple operation that just invokes a sequence of other unitary operations on a set of qubits, the adjoint may be computed by applying the adjoints of the sub-operations on the same qubits, in the reverse sequence.</span></span>

<span data-ttu-id="3d7b6-268">İşlem ifadesi verildiğinde, yeni bir işlem ifadesi `Adjoint` functor kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-268">Given an operation expression, a new operation expression may be formed using the `Adjoint` functor.</span></span>
<span data-ttu-id="3d7b6-269">Örneğin, `Adjoint QFT` `QFT` işleminin adjoint değerini belirtir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-269">For instance, `Adjoint QFT` designates the adjoint of the `QFT` operation.</span></span>
<span data-ttu-id="3d7b6-270">Yeni işlem, temel işlemle aynı imzaya ve türe sahip.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-270">The new operation has the same signature and type as the base operation.</span></span>
<span data-ttu-id="3d7b6-271">Özellikle de yeni işlem `Adjoint`sağlar ve yalnızca temel işlem olduysa `Controlled` izin verir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-271">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>

<span data-ttu-id="3d7b6-272">Adjoint functor kendi tersidir; Yani, `Adjoint Adjoint Op` `Op`her zaman aynıdır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-272">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled"></a><span data-ttu-id="3d7b6-273">Tarafından</span><span class="sxs-lookup"><span data-stu-id="3d7b6-273">Controlled</span></span>

<span data-ttu-id="3d7b6-274">Bir işlemin denetlenen sürümü, yalnızca tüm denetim qubits 'in belirtilen durumda olması durumunda temel işlemi etkili bir şekilde uygulayan yeni bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-274">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="3d7b6-275">Denetim qubitleri üst konumundayken, temel işlem üst konumun uygun bölümüne doğru şekilde uygulanır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-275">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="3d7b6-276">Bu nedenle, denetimli işlemler genellikle entanglement oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-276">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="3d7b6-277">Q # ' da, denetimli sürümler her zaman bir denetim qubit dizisi alır ve belirtilen durum her zaman denetim qubits 'in işlem (`PauliZ`) `One` durumunda $ \gre{1}$ ' a kadar olur.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-277">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
<span data-ttu-id="3d7b6-278">Diğer durumlara dayalı olarak denetlemek, denetimli işlemden önce denetim qubits 'e uygun Unitary işlemini uygulayarak ve sonra, denetimli işlemden sonra Unitary işleminin evirimini uygulayarak elde edilebilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-278">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
<span data-ttu-id="3d7b6-279">Örneğin, denetimli bir işlemden önce ve sonra bir denetim qubit 'e `X` işlemi uygulamak, bu qubit için `Zero` durumunda ($ \tus{0}$), işlemin denetimine neden olur; `H` işlemi ve sonrasında önce ve sonra,{0}{1}durum yerine-1 eigenvalue of Pauli X, $ \ket{-} \mathrel{: =} (\demet{2}-\tus`PauliZ`)/\sqrt `One` $ olan `PauliX` `One` durumunda bir denetim uygulayın.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-279">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="3d7b6-280">İşlem ifadesi verildiğinde, yeni bir işlem ifadesi `Controlled` functor kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-280">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="3d7b6-281">Yeni işlemin imzası, özgün işlemin imzasını temel alır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-281">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="3d7b6-282">Sonuç türü aynıdır, ancak giriş türü, ilk öğe olarak denetim qubit dizisini ve ikinci öğe olarak orijinal işlemin bağımsız değişkenlerini tutan bir qubit dizisi olan iki kayıt türüdür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-282">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="3d7b6-283">Yeni işlem `Controlled`destekler ve yalnızca özgün işlem olduysa `Adjoint` destekleyecektir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-283">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="3d7b6-284">Özgün işlem yalnızca tek bir bağımsız değişken alıyorsa, bu durumda tek demet denklik, burada yürütmeye gelir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-284">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="3d7b6-285">Örneğin, `Controlled X` `X` işleminin denetlenen sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-285">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span>
<span data-ttu-id="3d7b6-286">`X` `(Qubit => Unit is Adj + Ctl)`türüne sahip `Controlled X` türü `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; tek kayıt düzeni denkliği nedeniyle bu `((Qubit[], Qubit) => Unit is Adj + Ctl)`aynıdır.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-286">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="3d7b6-287">Temel işlem birkaç bağımsız değişken alıyorsa, bu işlemin denetlenen sürümünün ilgili bağımsız değişkenlerini, bir tanımlama grubu içine dönüştürmek için parantez içine almayı unutmayın.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-287">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="3d7b6-288">Örneğin, `Controlled Rz` `Rz` işleminin denetlenen sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-288">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span>
<span data-ttu-id="3d7b6-289">`Rz` `((Double, Qubit) => Unit is Adj + Ctl)`türüne sahip `Controlled Rz` `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`türüne sahip.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-289">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="3d7b6-290">Bu nedenle, `Controlled Rz(controls, (0.1, target))` geçerli bir `Controlled Rz` çağrısı olacaktır (`0.1, target`etrafında ayraçları aklınızda).</span><span class="sxs-lookup"><span data-stu-id="3d7b6-290">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="3d7b6-291">Başka bir örnek olarak, `CNOT(control, target)` `Controlled X([control], target)`olarak uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-291">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="3d7b6-292">Bir hedefin 2 denetim qubits (CCNOT) ile denetlenmesi gerekiyorsa `Controlled X([control1, control2], target)` deyiminizi kullanabiliriz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-292">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

### <a name="examples"></a><span data-ttu-id="3d7b6-293">Örnekler</span><span class="sxs-lookup"><span data-stu-id="3d7b6-293">Examples</span></span>

<span data-ttu-id="3d7b6-294">Bir Q # işleminin bu örneği, [ölçüm](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) örneğinden gelir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-294">This example of a Q# operation comes from the [Measurement](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement) sample.</span></span> <span data-ttu-id="3d7b6-295">İşlemler içinde, `H` ve `X`gibi bu qubits üzerinde qubits ayırabiliriz ve hisse alma işlemleri kullanabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="3d7b6-295">Within operations, we can allocate qubits and use quantum operations on those qubits such as `H` and `X`:</span></span>

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit() : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit
            set result = M(qubit);      // Measure the qubit
            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

<span data-ttu-id="3d7b6-296">Bir işlevin bu örneği, [Phasetahmin](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) örneğinden gelir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-296">This example of a function comes from the [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation) sample.</span></span> <span data-ttu-id="3d7b6-297">Yalnızca klasik kod içerir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-297">It contains purely classical code.</span></span> <span data-ttu-id="3d7b6-298">Yukarıdaki örneğin aksine, qubits ayrılmadığından ve hisse alma işlemleri kullanılmamış olduğunu görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-298">You can see that, unlike the example above, no qubits are allocated, and no quantum operations are used.</span></span>

```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function PointwiseProduct(left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

<span data-ttu-id="3d7b6-299">Ayrıca, [Reversıblelogicsensıs](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) örneğinden Bu örnekte olduğu gibi, bir işlevin işleme için qubits 'e geçirilmesi de mümkündür.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-299">It is also possible for a function to be passed qubits for processing, as in this example from the [ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis) sample.</span></span> <span data-ttu-id="3d7b6-300">Qubits işlevine geçirilir ve işlemek için kullanılır, ancak hiç bir nokta, hiçbir noktadan böyle bir şekilde değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="3d7b6-300">Qubits are passed to the function and used for processing, although at no point are the qubit states themselves modified.</span></span>

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates(
    qubits : Qubit[], 
    masks : MCMTMask[]) 
: MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
