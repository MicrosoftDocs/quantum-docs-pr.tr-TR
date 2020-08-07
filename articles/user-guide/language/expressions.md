---
title: İçindeki ifadelerQ#
description: Sabitleri, değişkenleri, işleçleri, işlemleri ve işlevleri ' de ifade olarak belirtme, başvurma ve birleştirme işlemlerini anlayın Q# .
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
no-loc:
- Q#
- $$v
ms.openlocfilehash: b6cc97dfee05dc843e213e84f17043714a8a9656
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869622"
---
# <a name="expressions-in-no-locq"></a><span data-ttu-id="c1866-103">İçindeki ifadelerQ#</span><span class="sxs-lookup"><span data-stu-id="c1866-103">Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="c1866-104">Sayısal Ifadeler</span><span class="sxs-lookup"><span data-stu-id="c1866-104">Numeric Expressions</span></span>

<span data-ttu-id="c1866-105">Sayısal ifadeler `Int` , veya türündeki ifadelerdir `BigInt` `Double` .</span><span class="sxs-lookup"><span data-stu-id="c1866-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="c1866-106">Diğer bir deyişle, tamsayı veya kayan noktalı sayılardır.</span><span class="sxs-lookup"><span data-stu-id="c1866-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="c1866-107">`Int`içindeki değişmez değerler Q# , bir dizi basamak olarak yazılmıştır.</span><span class="sxs-lookup"><span data-stu-id="c1866-107">`Int` literals in Q# are written as a sequence of digits.</span></span>
<span data-ttu-id="c1866-108">Onaltılık ve ikili tamsayılar desteklenir ve `0x` sırasıyla bir ve önekiyle yazılır `0b` .</span><span class="sxs-lookup"><span data-stu-id="c1866-108">Hexadecimal and binary integers are supported and written with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="c1866-109">`BigInt`içindeki değişmez değerler Q# sonunda `l` veya `L` soneke sahiptir.</span><span class="sxs-lookup"><span data-stu-id="c1866-109">`BigInt` literals in Q# have a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="c1866-110">Onaltılık büyük tamsayılar desteklenir ve "0x" önekiyle yazılır.</span><span class="sxs-lookup"><span data-stu-id="c1866-110">Hexadecimal big integers are supported and written with a "0x" prefix.</span></span>
<span data-ttu-id="c1866-111">Bu nedenle, tüm geçerli sabit değer kullanımları aşağıda verilmiştir `BigInt` :</span><span class="sxs-lookup"><span data-stu-id="c1866-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="c1866-112">`Double`içindeki değişmez değerler Q# , ondalık basamaklar kullanılarak yazılan kayan nokta sayılarıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="c1866-113">Bunlar ondalık bir nokta veya ya da ya da " `.` e" ya da "e" ya da bir üstel bölüm (yalnızca olası bir negatif işaret ve ondalık basamakların geçerli olması) ile yazılmış veya olmadan yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-113">They can be written with or without a decimal point, `.`, or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="c1866-114">Aşağıdakiler geçerli `Double` değişmez değerler: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="c1866-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="c1866-115">Herhangi bir öğe türünün dizi ifadesi verildiğinde, `Int` [`Length`](xref:microsoft.quantum.core.length) yerleşik işlevini kullanarak, dizi ifadesi parantez içine alınmış bir ifade oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-115">Given an array expression of any element type, you can form an `Int` expression using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses.</span></span>
<span data-ttu-id="c1866-116">Örneğin, `a` bir diziye bağlıysa, bir `Length(a)` tamsayı ifadesidir.</span><span class="sxs-lookup"><span data-stu-id="c1866-116">For example, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="c1866-117">, `b` Tamsayıların dizilerindeki bir diziyse, `Int[][]` `Length(b)` içindeki alt dizilerin sayısıdır `b` ve `Length(b[1])` içindeki ikinci alt dizideki tamsayıların sayısıdır `b` .</span><span class="sxs-lookup"><span data-stu-id="c1866-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="c1866-118">Aynı türde iki sayısal ifade verildiğinde, ikili işleçler,,, `+` `-` `*` ve `/` Yeni bir sayısal ifade oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="c1866-119">Yeni ifadenin türü, yapısal ifadelerin türleriyle aynıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-119">The type of the new expression is the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="c1866-120">İki tamsayı ifadesi verildiğinde, `^` Yeni bir tamsayı ifadesi oluşturmak için ikili işleci (Power) kullanın.</span><span class="sxs-lookup"><span data-stu-id="c1866-120">Given two integer expressions, use the binary operator `^` (power) to form a new integer expression.</span></span>
<span data-ttu-id="c1866-121">Benzer şekilde, `^` Yeni bir Double ifadesi oluşturmak için iki Double ifadesiyle da kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-121">Similarly, you can also use `^` with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="c1866-122">Son olarak, sol taraftaki `^` büyük bir tamsayı ve sağ taraftaki bir tamsayı kullanarak yeni bir büyük tamsayı ifadesi oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-122">Finally, you can use `^` with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="c1866-123">Bu durumda, ikinci parametrenin 32 bite sığması gerekir; Aksi takdirde, bir çalışma zamanı hatası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c1866-123">In this case, the second parameter must fit into 32 bits; if not, it raises a runtime error.</span></span>

<span data-ttu-id="c1866-124">İki tamsayı veya büyük tamsayı ifadesi verildiğinde, `%` (mod), `&&&` (BIT düzeyinde and), `|||` (bit düzeyinde OR) veya `^^^` (bit düzeyinde xor) işleçlerini kullanarak yeni bir tamsayı veya büyük tamsayı ifadesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c1866-124">Given two integer or big integer expressions, form a new integer or big integer expression using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="c1866-125">Sol tarafta bir tamsayı veya büyük tamsayı ifadesi ve sağ taraftaki bir tamsayı ifadesi verildiğinde, `<<<` `>>>` sol ifadeyle aynı türde yeni bir ifade oluşturmak için (aritmetik sol SHIFT) veya (aritmetik sağa kaydırma) işleçlerini kullanın.</span><span class="sxs-lookup"><span data-stu-id="c1866-125">Given either an integer or big integer expression on the left, and an integer expression on the right, use the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="c1866-126">Kaydırma işleminin ikinci parametresi (SHIFT miktarı) sıfırdan büyük veya sıfıra eşit olmalıdır; negatif kaydırma miktarları için davranış tanımsızdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="c1866-127">Her iki vardiya işlemi için de SHIFT miktarı 32 bite uyum sağlamalıdır; Aksi takdirde, bir çalışma zamanı hatası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c1866-127">The shift amount for either shift operation must also fit into 32 bits; if not, it raises a runtime error.</span></span>
<span data-ttu-id="c1866-128">Kaydırılan sayı bir tamsayı ise, kaydırma miktarı yorumlanır `mod 64` ; diğer bir deyişle, 1 vardiyası ve 65 vardiyası aynı etkiye sahiptir.</span><span class="sxs-lookup"><span data-stu-id="c1866-128">If the number shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="c1866-129">Hem tamsayı hem de büyük tamsayı değerleri için, vardiyalar aritmetik değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="c1866-130">Negatif bir değeri sol veya sağ olarak değiştirme negatif bir sayı ile sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="c1866-130">Shifting a negative value either left or right results in a negative number.</span></span>
<span data-ttu-id="c1866-131">Diğer bir deyişle, bir adım sola veya sağa kaydırma, sırasıyla 2 ile çarpılarak veya bölünerek aynıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-131">That is, shifting one step to the left or right is the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="c1866-132">Tamsayı bölme ve tamsayı mod, negatif sayılar için C# olarak aynı davranışı izler.</span><span class="sxs-lookup"><span data-stu-id="c1866-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="c1866-133">Yani, `a % b` her zaman aynı işarete sahiptir `a` ve `b * (a / b) + a % b` her zaman eşittir `a` .</span><span class="sxs-lookup"><span data-stu-id="c1866-133">That is, `a % b` always has the same sign as `a`, and `b * (a / b) + a % b` always equals `a`.</span></span>
<span data-ttu-id="c1866-134">Örnek:</span><span class="sxs-lookup"><span data-stu-id="c1866-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="c1866-135">5</span><span class="sxs-lookup"><span data-stu-id="c1866-135">5</span></span> | <span data-ttu-id="c1866-136">2</span><span class="sxs-lookup"><span data-stu-id="c1866-136">2</span></span> | <span data-ttu-id="c1866-137">2</span><span class="sxs-lookup"><span data-stu-id="c1866-137">2</span></span> | <span data-ttu-id="c1866-138">1</span><span class="sxs-lookup"><span data-stu-id="c1866-138">1</span></span>
 <span data-ttu-id="c1866-139">5</span><span class="sxs-lookup"><span data-stu-id="c1866-139">5</span></span> | <span data-ttu-id="c1866-140">-2</span><span class="sxs-lookup"><span data-stu-id="c1866-140">-2</span></span> | <span data-ttu-id="c1866-141">-2</span><span class="sxs-lookup"><span data-stu-id="c1866-141">-2</span></span> | <span data-ttu-id="c1866-142">1</span><span class="sxs-lookup"><span data-stu-id="c1866-142">1</span></span>
 <span data-ttu-id="c1866-143">-5</span><span class="sxs-lookup"><span data-stu-id="c1866-143">-5</span></span> | <span data-ttu-id="c1866-144">2</span><span class="sxs-lookup"><span data-stu-id="c1866-144">2</span></span> | <span data-ttu-id="c1866-145">-2</span><span class="sxs-lookup"><span data-stu-id="c1866-145">-2</span></span> | <span data-ttu-id="c1866-146">-1</span><span class="sxs-lookup"><span data-stu-id="c1866-146">-1</span></span>
 <span data-ttu-id="c1866-147">-5</span><span class="sxs-lookup"><span data-stu-id="c1866-147">-5</span></span> | <span data-ttu-id="c1866-148">-2</span><span class="sxs-lookup"><span data-stu-id="c1866-148">-2</span></span> | <span data-ttu-id="c1866-149">2</span><span class="sxs-lookup"><span data-stu-id="c1866-149">2</span></span> | <span data-ttu-id="c1866-150">-1</span><span class="sxs-lookup"><span data-stu-id="c1866-150">-1</span></span>

<span data-ttu-id="c1866-151">Büyük tamsayı bölme ve mod işlemleri aynı şekilde çalışır.</span><span class="sxs-lookup"><span data-stu-id="c1866-151">Big integer division and modulus operations work the same way.</span></span>

<span data-ttu-id="c1866-152">Herhangi bir sayısal ifade verildiğinde birli işlecini kullanarak yeni bir ifade oluşturabilirsiniz `-` .</span><span class="sxs-lookup"><span data-stu-id="c1866-152">Given any numeric expression, you can form a new expression using the `-` unary operator.</span></span>
<span data-ttu-id="c1866-153">Yeni ifade, anayent ifadesiyle aynı türde.</span><span class="sxs-lookup"><span data-stu-id="c1866-153">The new expression is the same type as the constituent expression.</span></span>

<span data-ttu-id="c1866-154">Herhangi bir tamsayı veya büyük tamsayı ifadesi verildiğinde, `~~~` (bit düzeyinde tamamlayıcı) birli işlecini kullanarak aynı türde yeni bir ifade oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-154">Given any integer or big integer expression, you can form a new expression of the same type using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="c1866-155">Boole İfadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-155">Boolean Expressions</span></span>

<span data-ttu-id="c1866-156">İki `Bool` değişmez değer de `true` ve ' dir `false` .</span><span class="sxs-lookup"><span data-stu-id="c1866-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="c1866-157">Aynı ilkel türdeki iki ifade verildiğinde, `==` ve `!=` ikili işleçler bir ifade oluşturmak için kullanılabilir `Bool` .</span><span class="sxs-lookup"><span data-stu-id="c1866-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="c1866-158">İki ifade eşitse true, değilse false şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="c1866-158">The expression is true if the two expressions are equal and false if not.</span></span>

<span data-ttu-id="c1866-159">Kullanıcı tanımlı türlerin değerleri karşılaştırılamayabilir, yalnızca sarmalanmamış değerler karşılaştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="c1866-160">Örneğin, "sarmalama" işlecini kullanma `!` ( [içindeki Q# türlerde ](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)ayrıntılı olarak açıklanmıştır)</span><span class="sxs-lookup"><span data-stu-id="c1866-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="c1866-161">Değerler için eşitlik karşılaştırması `Qubit` kimlik eşitlik, yani iki ifadenin aynı qubit 'i tanımlamasına bakılmaksızın.</span><span class="sxs-lookup"><span data-stu-id="c1866-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="c1866-162">İki qubits 'in durumları karşılaştırılmaz, erişilmez, ölçülemez veya bu karşılaştırma tarafından değiştirilmez.</span><span class="sxs-lookup"><span data-stu-id="c1866-162">The states of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="c1866-163">Değerler için eşitlik karşılaştırması `Double` , yuvarlama etkileri nedeniyle yanıltıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="c1866-164">Örneğin, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="c1866-164">For example, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="c1866-165">Herhangi iki sayısal ifade verildiğinde,,, ve ikili işleçleri,,, `>` `<` `>=` ve `<=` ilk ifade sırasıyla sıfırdan büyük, küçüktür, büyüktür veya eşittir veya ikinci ifadeden daha küçük veya eşit olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="c1866-166">Herhangi iki Boolean ifadesi verildiğinde, `and` iki ifadenin her ikisi de doğru olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için ikili işleci kullanın.</span><span class="sxs-lookup"><span data-stu-id="c1866-166">Given any two Boolean expressions, use the `and` binary operator to construct a new Boolean expression that is true if both of the two expressions are true.</span></span> <span data-ttu-id="c1866-167">Benzer şekilde, işleci kullanıldığında, `or` iki deyimden biri true olduğunda true olan bir ifade oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c1866-167">Likewise, using the `or` operator creates an expression that is true if either of the two expressions is true.</span></span>

<span data-ttu-id="c1866-168">Herhangi bir Boole ifadesi verildiğinde, `not` birli işleç yanlış olduğunda, doğru olan yeni bir Boole ifadesi oluşturmak için birli işleç kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-168">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="c1866-169">Dize ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-169">String expressions</span></span>

<span data-ttu-id="c1866-170">Q#`fail`deyimde ( [Denetim akışında](xref:microsoft.quantum.guide.controlflow#fail-statement)açıklanmıştır) ve standart işlevde dizelerin kullanılmasına izin verir [`Message`](xref:microsoft.quantum.intrinsic.message) .</span><span class="sxs-lookup"><span data-stu-id="c1866-170">Q# allows strings to be used in the `fail` statement (explained in [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span> <span data-ttu-id="c1866-171">İkinci öğesinin belirli davranışı kullanılan simülatöre bağlıdır, ancak genellikle bir program sırasında çağrıldığında ana bilgisayar konsoluna bir ileti yazar Q# .</span><span class="sxs-lookup"><span data-stu-id="c1866-171">The specific behavior of the latter depends on the simulator used but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="c1866-172">İçindeki dizeler Q# değişmez değerler ya da enterpolasyonlardır.</span><span class="sxs-lookup"><span data-stu-id="c1866-172">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="c1866-173">Dize sabit değerleri çoğu dilde basit dize sabit değerlerine benzer: çift tırnak içine alınmış bir Unicode karakter dizisi `" "` .</span><span class="sxs-lookup"><span data-stu-id="c1866-173">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double-quotes `" "`.</span></span>
<span data-ttu-id="c1866-174">Bir dizenin içinde, `\` çift tırnak karakterini ( `\"` ) kaçış veya New-Line ( `\n` ), bir satır başı ( `\r` ) veya Tab ( `\t` ) eklemek için ters eğik çizgi karakterini kullanın.</span><span class="sxs-lookup"><span data-stu-id="c1866-174">Inside of a string, use the backslash character `\` to escape a double-quote character (`\"`), or to insert a new-line ( `\n` ), a carriage return (`\r`), or a tab (`\t`).</span></span>
<span data-ttu-id="c1866-175">Örnek:</span><span class="sxs-lookup"><span data-stu-id="c1866-175">For example:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="c1866-176">Ara değerli dizeler</span><span class="sxs-lookup"><span data-stu-id="c1866-176">Interpolated strings</span></span>

<span data-ttu-id="c1866-177">Q#Dize enterpolasyonları için sözdizimi, C# sözdiziminin bir alt kümesidir.</span><span class="sxs-lookup"><span data-stu-id="c1866-177">The Q# syntax for string interpolations is a subset of the C# syntax.</span></span> <span data-ttu-id="c1866-178">Aşağıdakiler ile ilgili önemli noktaları aşağıda verilmiştir Q# :</span><span class="sxs-lookup"><span data-stu-id="c1866-178">Following are the key points as they pertain to Q#:</span></span>

* <span data-ttu-id="c1866-179">Bir dize sabit değerini, enterpolasyonlu bir dize olarak tanımlamak için, `$` simgeyi simgesiyle önüne ekleyin.</span><span class="sxs-lookup"><span data-stu-id="c1866-179">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="c1866-180">`$`Ve arasında `"` bir dize sabiti Başlatan boşluk olamaz.</span><span class="sxs-lookup"><span data-stu-id="c1866-180">There can be no white space between the `$` and the `"` that starts a string literal.</span></span>

* <span data-ttu-id="c1866-181">Aşağıdaki örnek, [`Message`](xref:microsoft.quantum.intrinsic.message) diğer ifadelerle birlikte, bir ölçünün sonucunu konsola yazmak için fonksiyonunu kullanan temel bir örnektir Q# .</span><span class="sxs-lookup"><span data-stu-id="c1866-181">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```

* <span data-ttu-id="c1866-182">Geçerli Q# bir ifade, enterpolasyonlu bir dizede görünebilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-182">Any valid Q# expression may appear in an interpolated string.</span></span>

* <span data-ttu-id="c1866-183">Bir enterpolasyonlu dize içindeki ifadeler Q# C# söz dizimini değil söz dizimini izler.</span><span class="sxs-lookup"><span data-stu-id="c1866-183">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span> <span data-ttu-id="c1866-184">En önemli ayrım, tam Q# (çok satırlı) enterpolasyonlu dizeleri desteklemedir.</span><span class="sxs-lookup"><span data-stu-id="c1866-184">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>

<span data-ttu-id="c1866-185">C# sözdizimi hakkında daha fazla bilgi için bkz. [*enterpolasyonlu dizeler*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="c1866-185">For more details about the C# syntax, see [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>

## <a name="range-expressions"></a><span data-ttu-id="c1866-186">Aralık Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-186">Range Expressions</span></span>

<span data-ttu-id="c1866-187">, Ve olmak üzere üç ifade verildiğinde, `Int` `start` `step` `stop` ifadesi `start .. step .. stop` ilk öğesi olan bir Aralık ifadesi, `start` ikinci öğe ise, üçüncü öğe, vb., `start+step` `start+step+step` geçene kadar `stop` .</span><span class="sxs-lookup"><span data-stu-id="c1866-187">Given any three `Int` expressions `start`, `step`, and `stop`, the expression `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, and so on, until you pass `stop`.</span></span>
<span data-ttu-id="c1866-188">Örneğin, pozitif ve olduğunda bir Aralık boş olabilir `step` `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="c1866-188">A range may be empty if, for example, `step` is positive and `stop < start`.</span></span>

<span data-ttu-id="c1866-189">Aralık her iki ucu da dahil değildir.</span><span class="sxs-lookup"><span data-stu-id="c1866-189">The range is inclusive at both ends.</span></span> <span data-ttu-id="c1866-190">Diğer bir deyişle, ve arasındaki fark `start` `stop` bir tamsayı ise `step` , aralığın son öğesi olacaktır `stop` .</span><span class="sxs-lookup"><span data-stu-id="c1866-190">That is, if the difference between `start` and `stop` is an integer multiple of `step`, the last element of the range will be `stop`.</span></span>

<span data-ttu-id="c1866-191">Her iki `Int` ifade de `start` ve `stop` ifade verilen `start .. stop` bir Aralık ifadesi `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="c1866-191">Given any two `Int` expressions `start` and `stop`, the expression `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="c1866-192">Önünde ve `step` ' den küçük olsa bile, örtük ' ın + 1 olduğunu unutmayın `stop` `start` . böyle bir durumda, Aralık boş olur.</span><span class="sxs-lookup"><span data-stu-id="c1866-192">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="c1866-193">Bazı örnek aralıklar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="c1866-193">Some example ranges are:</span></span>

- <span data-ttu-id="c1866-194">`1..3`1, 2, 3 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-194">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="c1866-195">`2..2..5`2, 4 aralığındadır.</span><span class="sxs-lookup"><span data-stu-id="c1866-195">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="c1866-196">`2..2..6`2, 4, 6 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-196">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="c1866-197">`6..-2..2`6, 4, 2 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-197">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="c1866-198">`2..1`boş aralıktır.</span><span class="sxs-lookup"><span data-stu-id="c1866-198">`2..1` is the empty range.</span></span>
- <span data-ttu-id="c1866-199">`2..6..7`Aralık 2 ' dir.</span><span class="sxs-lookup"><span data-stu-id="c1866-199">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="c1866-200">`2..2..1`boş aralıktır.</span><span class="sxs-lookup"><span data-stu-id="c1866-200">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="c1866-201">`1..-1..2`boş aralıktır.</span><span class="sxs-lookup"><span data-stu-id="c1866-201">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="c1866-202">Qubit Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-202">Qubit Expressions</span></span>

<span data-ttu-id="c1866-203">Tek `Qubit` ifadeler, `Qubit` dizilerin değerlerine veya dizi öğelerine bağlanan sembollerdir `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c1866-203">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="c1866-204">Değişmez değer yok `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="c1866-204">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="c1866-205">Pauli Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-205">Pauli Expressions</span></span>

<span data-ttu-id="c1866-206">Dört değeri,,, `Pauli` `PauliI` `PauliX` `PauliY` ve `PauliZ` , tüm geçerli `Pauli` ifadelerdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-206">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="c1866-207">Bunun dışında, tek ifadeler, `Pauli` `Pauli` dizilere ait değerlere veya dizi öğelerine bağlanan sembollerdir `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="c1866-207">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="c1866-208">Sonuç Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-208">Result Expressions</span></span>

<span data-ttu-id="c1866-209">İki `Result` değer `One` ve `Zero` , geçerli `Result` ifadelerdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-209">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="c1866-210">Bunun dışında, tek ifadeler, `Result` `Result` dizilere ait değerlere veya dizi öğelerine bağlanan sembollerdir `Result` .</span><span class="sxs-lookup"><span data-stu-id="c1866-210">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="c1866-211">Özellikle, `One` tamsayıyla aynı olmadığını ve aralarında doğrudan dönüşüm olmadığını unutmayın `1` .</span><span class="sxs-lookup"><span data-stu-id="c1866-211">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="c1866-212">Aynı, ve için de `Zero` geçerlidir `0` .</span><span class="sxs-lookup"><span data-stu-id="c1866-212">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="c1866-213">Demet Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-213">Tuple Expressions</span></span>

<span data-ttu-id="c1866-214">Tanımlama grubu sabit değeri, virgülle ayrılmış şekilde, uygun türdeki öğe ifadelerinin dizelerdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-214">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in parentheses.</span></span>
<span data-ttu-id="c1866-215">Örneğin, `(1, One)` bir `(Int, Result)` ifadedir.</span><span class="sxs-lookup"><span data-stu-id="c1866-215">For example, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="c1866-216">Değişmez değerler dışında, tek demet ifadeleri demet değerlerine, demet dizilerinin dizi öğelerine ve tanımlama grupları döndüren çağrılabilir çağırmaları olan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-216">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="c1866-217">Kullanıcı tanımlı tür Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-217">User-Defined Type Expressions</span></span>

<span data-ttu-id="c1866-218">Kullanıcı tanımlı bir türün sabit değeri tür adından, ardından türün temel demet türünün bir tanımlama grubu değişmez değerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="c1866-218">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="c1866-219">Örneğin, `IntPair` temelli Kullanıcı tanımlı bir tür ise `(Int, Int)` , `IntPair(2, 3)` Bu türün geçerli bir sabit değeri olur.</span><span class="sxs-lookup"><span data-stu-id="c1866-219">For example, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` is a valid literal of that type.</span></span>

<span data-ttu-id="c1866-220">Değişmez değerler dışında, Kullanıcı tanımlı bir türün tek ifadeleri, bu türün değerlerine, bu türden dizilerin dizi öğelerine ve bu türü döndüren çağrılabilir çağırmaları olan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-220">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="c1866-221">Ifade kaydırmayı geri al</span><span class="sxs-lookup"><span data-stu-id="c1866-221">Unwrap Expressions</span></span>

<span data-ttu-id="c1866-222">Q#' De, geri sarım işleci sondaki bir ünlem işaretidir `!` .</span><span class="sxs-lookup"><span data-stu-id="c1866-222">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="c1866-223">Örneğin, `IntPair` temel alınan türe sahip kullanıcı tanımlı bir türdür `(Int, Int)` ve `s` değeri olan bir değişkense, `IntPair(2, 3)` `s!` olur `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="c1866-223">For example, if `IntPair` is a user-defined type with the underlying type `(Int, Int)` and `s` is a variable with value `IntPair(2, 3)`, then `s!` is `(2, 3)`.</span></span>

<span data-ttu-id="c1866-224">Diğer Kullanıcı tanımlı türler bakımından tanımlanan Kullanıcı tanımlı türler için, Unwrap işlecini yineleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-224">For user-defined types defined in terms of other user-defined types, you can repeat the unwrap operator.</span></span> <span data-ttu-id="c1866-225">Örneğin, `s!!` paketlenmiş ve sarmalanmamış değeri gösterir `s` .</span><span class="sxs-lookup"><span data-stu-id="c1866-225">For example, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="c1866-226">Bu nedenle, `WrappedPair` temel alınan türe sahip kullanıcı tanımlı bir türdür `IntPair` ve `t` değeri olan bir değişkense, `WrappedPair(IntPair(1,2))` `t!!` olur `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="c1866-226">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` is `(1,2)`.</span></span>

<span data-ttu-id="c1866-227">`!`İşleç, `[]` dizi dizini oluşturma ve dilimleme için dışındaki diğer işleçlerden daha yüksek önceliğe sahiptir.</span><span class="sxs-lookup"><span data-stu-id="c1866-227">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="c1866-228">`!`ve, `[]` pozitif bir deyişle, `a[i]![3]` şöyle okunurdur `((a[i])!)[3]` : `i` . öğesini alın `a` , sarmalayın ve sarmalanmamış değerin 3. öğesini (bir dizi olması gerekir) alın.</span><span class="sxs-lookup"><span data-stu-id="c1866-228">`!` and `[]` bind positionally; that is, `a[i]![3]` is read as `((a[i])!)[3]`: take the `i`th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="c1866-229">`!`İşlecin önceliği belirgin olmayan bir etkiye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-229">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="c1866-230">Bir işlev veya işlem sarmalanmamış bir değer döndürürse, bağımsız değişken grubu, sarmalama yerine çağrıya bağlamak için işlev veya işlem çağrısının parantez içine alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="c1866-230">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="c1866-231">Örnek:</span><span class="sxs-lookup"><span data-stu-id="c1866-231">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="c1866-232">Dizi Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-232">Array Expressions</span></span>

<span data-ttu-id="c1866-233">Dizi sabit değeri, virgülle ayrılmış bir veya daha fazla öğe ifadesi dizisi parantez içine alınmıştır `[]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-233">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in square brackets `[]`.</span></span>
<span data-ttu-id="c1866-234">Tüm öğeler aynı türle uyumlu olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-234">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="c1866-235">Aynı türde iki dizi verildiğinde, `+` iki dizinin birleşimi olan yeni bir dizi oluşturmak için ikili işlecini kullanın.</span><span class="sxs-lookup"><span data-stu-id="c1866-235">Given two arrays of the same type, use the binary `+` operator to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="c1866-236">Örneğin, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="c1866-236">For example, `[1,2,3] + [4,5,6]` = `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="c1866-237">Dizi oluşturma</span><span class="sxs-lookup"><span data-stu-id="c1866-237">Array Creation</span></span>

<span data-ttu-id="c1866-238">Bir tür ve ifade verildiğinde `Int` , `new` verilen boyutun yeni bir dizisini ayırmak için işlecini kullanın.</span><span class="sxs-lookup"><span data-stu-id="c1866-238">Given a type and an `Int` expression, use the `new` operator to allocate a new array of the given size.</span></span>
<span data-ttu-id="c1866-239">Örneğin, `new Int[i + 1]` öğeleri içeren yeni bir `Int` dizi ayırır `i + 1` .</span><span class="sxs-lookup"><span data-stu-id="c1866-239">For example, `new Int[i + 1]` allocates a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="c1866-240">Boş dizi değişmez değerlerine (gibi) `[]` izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="c1866-240">Empty array literals, such as `[]`, are not allowed.</span></span>
<span data-ttu-id="c1866-241">Bunun yerine, `new T[0]` `T` uygun bir tür için yer tutucu olan öğesini kullanarak sıfır uzunluğunda bir dizi oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-241">Instead, you can create an array of length zero by using `new T[0]`, where `T` is a placeholder for a suitable type.</span></span>

<span data-ttu-id="c1866-242">Yeni bir dizinin öğeleri, türe bağlı bir varsayılan değere başlatırlar.</span><span class="sxs-lookup"><span data-stu-id="c1866-242">The elements of a new array initialize to a type-dependent default value.</span></span>
<span data-ttu-id="c1866-243">Çoğu durumda, bu bazı sıfır çeşitlerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="c1866-243">In most cases, this is some variation of zero.</span></span>

<span data-ttu-id="c1866-244">Varlıklara başvurular olan qubits ve callables için makul bir varsayılan değer yoktur.</span><span class="sxs-lookup"><span data-stu-id="c1866-244">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="c1866-245">Bu nedenle, varsayılan olarak, bir çalışma zamanı hatasına neden olmadan, C# veya Java gibi dillerdeki bir null başvuruya benzer şekilde kullanamazsınız.</span><span class="sxs-lookup"><span data-stu-id="c1866-245">Thus, for these types, the default is an invalid reference that you cannot use without causing a runtime error, similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="c1866-246">, Öğelerini güvenli bir şekilde kullanabilmeniz için qubits veya callables içeren diziler varsayılan olmayan değerlerle başlatılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-246">Arrays containing qubits or callables must be initialized with non-default values before you can use their elements safely.</span></span> <span data-ttu-id="c1866-247">Uygun başlatma yordamları için bkz <xref:microsoft.quantum.arrays> ..</span><span class="sxs-lookup"><span data-stu-id="c1866-247">For suitable initialization routines, see <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="c1866-248">Her türün varsayılan değerleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="c1866-248">The default values for each type are:</span></span>

<span data-ttu-id="c1866-249">Tür</span><span class="sxs-lookup"><span data-stu-id="c1866-249">Type</span></span> | <span data-ttu-id="c1866-250">Varsayılan</span><span class="sxs-lookup"><span data-stu-id="c1866-250">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="c1866-251">_geçersiz qubit_</span><span class="sxs-lookup"><span data-stu-id="c1866-251">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="c1866-252">Boş Aralık,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="c1866-252">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="c1866-253">_geçersiz çağrılabilir_</span><span class="sxs-lookup"><span data-stu-id="c1866-253">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="c1866-254">Demet türleri öğeyi by öğesi olarak başlatır.</span><span class="sxs-lookup"><span data-stu-id="c1866-254">Tuple types initialize element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="c1866-255">Dizi öğeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-255">Array Elements</span></span>

<span data-ttu-id="c1866-256">Dizi ifadesi ve bir ifade verildiğinde `Int` , Array öğesi işlecini kullanarak yeni bir ifade oluşturur `[]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-256">Given an array expression and an `Int` expression, form a new expression using the array element operator `[]`.</span></span>
<span data-ttu-id="c1866-257">Yeni ifade, dizinin öğe türüyle aynı türde.</span><span class="sxs-lookup"><span data-stu-id="c1866-257">The new expression is the same type as the element type of the array.</span></span>
<span data-ttu-id="c1866-258">Örneğin, türünde bir `a` diziye bağlanmışsa `Double` , `a[4]` bir `Double` ifadedir.</span><span class="sxs-lookup"><span data-stu-id="c1866-258">For example, if `a` is bound to an array of type `Double`, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="c1866-259">Dizi ifadesi basit bir tanımlayıcı değilse, bir öğeyi seçmek için ayraçları parantez içine almalısınız.</span><span class="sxs-lookup"><span data-stu-id="c1866-259">If the array expression is not a simple identifier, you must enclose it in parentheses to select an element.</span></span>
<span data-ttu-id="c1866-260">Örneğin, `a` ve `b` her iki dizi dizisise `Int` , birleştirme işleminden bir öğe şöyle ifade edilir:</span><span class="sxs-lookup"><span data-stu-id="c1866-260">For example, if `a` and `b` are both arrays of type `Int`, an element from the concatenation is expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="c1866-261">İçindeki tüm diziler Q# sıfır tabanlıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-261">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="c1866-262">Diğer bir deyişle, bir dizinin ilk öğesi `a` her zaman olur `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-262">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="c1866-263">Dizi dilimleri</span><span class="sxs-lookup"><span data-stu-id="c1866-263">Array Slices</span></span>

<span data-ttu-id="c1866-264">Dizi ifadesi ve bir ifade verildiğinde `Range` , dizi dilimi işlecini kullanarak yeni bir ifade oluşturur `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-264">Given an array expression and a `Range` expression, form a new expression using the array slice operator `[ ]`.</span></span>
<span data-ttu-id="c1866-265">Yeni ifade, dizisiyle aynı türdür ve tarafından tanımlanan sırada öğesi tarafından dizin oluşturulan dizi öğelerini içerir `Range` `Range` .</span><span class="sxs-lookup"><span data-stu-id="c1866-265">The new expression is the same type as the array and contains the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="c1866-266">Örneğin, `a` türünde bir diziye bağlıysa `Double` ,, `a[3..-1..0]` `Double[]` `a` ancak içinde göründükleri şekilde ters sırada olan ilk dört öğeyi içeren bir ifadedir `a` .</span><span class="sxs-lookup"><span data-stu-id="c1866-266">For example, if `a` is bound to an array of type `Double`, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="c1866-267">`Range`Boşsa, sonuçta elde edilen dizi dilimi sıfır uzunluktadır.</span><span class="sxs-lookup"><span data-stu-id="c1866-267">If the `Range` is empty, then the resulting array slice is zero length.</span></span>

<span data-ttu-id="c1866-268">Başvuran dizi öğelerinde olduğu gibi, dizi ifadesi basit bir tanımlayıcı değilse, onu dilimlemek için parantez içine almalısınız.</span><span class="sxs-lookup"><span data-stu-id="c1866-268">Just as with referencing array elements, if the array expression is not a simple identifier, you must enclose it in parentheses to slice it.</span></span>
<span data-ttu-id="c1866-269">Örneğin, `a` ve `b` her iki dizi dizisise `Int` , birleştirme işleminden alınan bir dilim şöyle ifade edilir:</span><span class="sxs-lookup"><span data-stu-id="c1866-269">For example, if `a` and `b` are both arrays of type `Int`, a slice from the concatenation is expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="c1866-270">Çıkarılan başlangıç/bitiş değerleri</span><span class="sxs-lookup"><span data-stu-id="c1866-270">Inferred start/end values</span></span>

<span data-ttu-id="c1866-271">[0,8 sürümümüzden](xref:microsoft.quantum.relnotes)başlayarak, Aralık Dilimleme için bağlamsal ifadeleri destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="c1866-271">Starting with our [0.8 release](xref:microsoft.quantum.relnotes), we support contextual expressions for range slicing.</span></span> <span data-ttu-id="c1866-272">Özellikle bir Aralık Dilimleme ifadesi bağlamında Aralık başlangıcı ve bitiş değerlerini atlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-272">In particular, you may omit range start and end values in the context of a range slicing expression.</span></span> <span data-ttu-id="c1866-273">Bu durumda, derleyici aralığa yönelik istenen sınırlayıcıları çıkarması için aşağıdaki kuralları uygular:</span><span class="sxs-lookup"><span data-stu-id="c1866-273">In that case, the compiler applies the following rules to infer the intended delimiters for the range:</span></span>

* <span data-ttu-id="c1866-274">Aralık *başlangıcı* değeri atlanırsa, çıkarılan başlangıç değeri</span><span class="sxs-lookup"><span data-stu-id="c1866-274">If the range *start* value is omitted, then the inferred start value</span></span>
  * <span data-ttu-id="c1866-275">bir adım belirtilmemişse veya belirtilen adım pozitif ise sıfır olur.</span><span class="sxs-lookup"><span data-stu-id="c1866-275">is zero if no step is specified or the specified step is positive.</span></span>  
  * <span data-ttu-id="c1866-276">, belirtilen adım negatifse, dilimli dizinin uzunluğu eksi bir değer.</span><span class="sxs-lookup"><span data-stu-id="c1866-276">is the length of the sliced array minus one if the specified step is negative.</span></span>

* <span data-ttu-id="c1866-277">Aralık *bitiş* değeri atlanırsa, çıkarılan bitiş değeri</span><span class="sxs-lookup"><span data-stu-id="c1866-277">If the range *end* value is omitted, then the inferred end value</span></span>
  * <span data-ttu-id="c1866-278">, hiçbir adım belirtilmediyse veya belirtilen adım pozitifse dilimli dizinin uzunluğu eksi bir değer.</span><span class="sxs-lookup"><span data-stu-id="c1866-278">is the length of the sliced array minus one if no step is specified or the specified step is positive.</span></span>
  * <span data-ttu-id="c1866-279">, belirtilen adım negatifse sıfırdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-279">is zero if the specified step is negative.</span></span>

<span data-ttu-id="c1866-280">Bazı örnekler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="c1866-280">Some examples are:</span></span>

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a><span data-ttu-id="c1866-281">Kopyalama ve güncelleştirme Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-281">Copy-and-Update Expressions</span></span>

<span data-ttu-id="c1866-282">Tüm Q# türler değer türleri olduğundan (biraz özel bir rol alan qubits ile), bir değer bir simgeye bağlandığında veya bir sembol yeniden bağlandığında bir "kopya" oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c1866-282">Since all Q# types are value types (with the qubits taking a somewhat special role), formally a "copy" is created when a value is bound to a symbol or when a symbol is rebound.</span></span> <span data-ttu-id="c1866-283">Şöyle ki, davranışı Q# atama işleci kullanılarak oluşturulmuş bir kopya ile aynı olur.</span><span class="sxs-lookup"><span data-stu-id="c1866-283">That is to say, the behavior of Q# is the same as if a copy were created using an assignment operator.</span></span> 

<span data-ttu-id="c1866-284">Tabii ki, pratikte yalnızca ilgili parçalar gerektiği şekilde yeniden oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="c1866-284">Of course, in practice, only the relevant pieces are recreated as needed.</span></span> <span data-ttu-id="c1866-285">Bu, dizi öğelerini güncelleştirmek mümkün olmadığından dizileri kopyalamayı etkiler.</span><span class="sxs-lookup"><span data-stu-id="c1866-285">This affects how you copy arrays because it is not possible to update array items.</span></span> <span data-ttu-id="c1866-286">Var olan bir diziyi değiştirmek için bir *kopyalama ve güncelleştirme* mekanizmasının kullanılmasını gerekir.</span><span class="sxs-lookup"><span data-stu-id="c1866-286">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="c1866-287">Var olan bir diziden, işleçlerini ve işlecini kullanan *kopyalama ve güncelleştirme* ifadeleri aracılığıyla yeni bir dizi oluşturabilirsiniz `w/` `<-` .</span><span class="sxs-lookup"><span data-stu-id="c1866-287">You can create a new array from an existing array via *copy-and-update* expressions, which use the operators `w/` and `<-`.</span></span>
<span data-ttu-id="c1866-288">Bir kopya ve güncelleştirme ifadesi formun bir ifadesidir `expression1 w/ expression2 <- expression3` , burada</span><span class="sxs-lookup"><span data-stu-id="c1866-288">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where</span></span>

* <span data-ttu-id="c1866-289">`expression1``T[]`bir tür için tür olmalıdır `T` .</span><span class="sxs-lookup"><span data-stu-id="c1866-289">`expression1` must be type `T[]` for some type `T`.</span></span>
* <span data-ttu-id="c1866-290">`expression2`' de belirtilen dizide hangi dizinlerin değiştirileceğini tanımlar `expression1` .</span><span class="sxs-lookup"><span data-stu-id="c1866-290">`expression2` defines which indices in the array specified in `expression1` to modify.</span></span> <span data-ttu-id="c1866-291">`expression2`tür `Int` ya da tür olmalıdır `Range` .</span><span class="sxs-lookup"><span data-stu-id="c1866-291">`expression2` must be either type `Int` or type `Range`.</span></span>
* <span data-ttu-id="c1866-292">`expression3``expression1`, içinde belirtilen indeksler temelinde içindeki öğeleri güncelleştirmek için kullanılan değerdir `expression2` .</span><span class="sxs-lookup"><span data-stu-id="c1866-292">`expression3` is the value(s) used to update elements in `expression1`, based on the indices specified in `expression2`.</span></span> <span data-ttu-id="c1866-293">`expression2`Tür ise `Int` , tür olmalıdır `expression3` `T` .</span><span class="sxs-lookup"><span data-stu-id="c1866-293">If `expression2` is type `Int`, `expression3` must be type `T`.</span></span> <span data-ttu-id="c1866-294">`expression2`Tür ise `Range` , tür olmalıdır `expression3` `T[]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-294">If `expression2` is type `Range`, `expression3` must be type `T[]`.</span></span>

<span data-ttu-id="c1866-295">Örneğin, Copy ve Update ifadesi, ' `arr w/ idx <- value` `arr` `idx` deki değer (ler) e ayarlanan tarafından belirtilen öğe (ler) hariç, içindeki karşılık gelen öğelere ayarlanmış tüm öğeleri içeren yeni bir dizi oluşturur `value` .</span><span class="sxs-lookup"><span data-stu-id="c1866-295">For example, the copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding elements in `arr`, except for the element(s) specified by `idx`, which is set to the value(s) in `value`.</span></span> 

<span data-ttu-id="c1866-296">Verilen `arr` diziyi içeriyorsa `[0,1,2,3]` ,</span><span class="sxs-lookup"><span data-stu-id="c1866-296">Given `arr` contains the array `[0,1,2,3]`, then</span></span> 

- <span data-ttu-id="c1866-297">`arr w/ 0 <- 10`dizi `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-297">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="c1866-298">`arr w/ 2 <- 10`dizi `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-298">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="c1866-299">`arr w/ 0..2..3 <- [10,12]`dizi `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-299">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="c1866-300">Adlandırılmış öğeler için kopyalama ve güncelleştirme ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-300">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="c1866-301">Kullanıcı tanımlı türlerde adlandırılmış öğeler için benzer ifadeler mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="c1866-301">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="c1866-302">Örneğin, türü göz önünde bulundurun</span><span class="sxs-lookup"><span data-stu-id="c1866-302">For example, consider the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="c1866-303">`c`Türü değerini içeriyorsa `Complex(1., -1.)` ,, `c w/ Re <- 0.` olarak değerlendirilen türünde bir ifadedir `Complex` `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="c1866-303">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="c1866-304">Düzensiz Diziler</span><span class="sxs-lookup"><span data-stu-id="c1866-304">Jagged Arrays</span></span>

<span data-ttu-id="c1866-305">Bazen "dizi dizisi" olarak adlandırılan pürüzlü bir dizi, öğeleri dizi dizileri olan bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="c1866-305">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="c1866-306">Pürüzlü bir dizinin öğeleri farklı boyutlarda olabilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-306">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="c1866-307">Aşağıdaki örnek, çarpma tablosunu temsil eden pürüzlü bir dizinin nasıl bildirilemeyeceğini ve başlatılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="c1866-307">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a><span data-ttu-id="c1866-308">Callables dizileri</span><span class="sxs-lookup"><span data-stu-id="c1866-308">Arrays of callables</span></span> 

<span data-ttu-id="c1866-309">Ayrıca, callables dizisi de oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-309">You can also create an array of callables.</span></span>

* <span data-ttu-id="c1866-310">Ortak öğe türü bir işlem ya da işlev türü ise, tüm öğeler aynı giriş ve çıkış türlerine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-310">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
* <span data-ttu-id="c1866-311">Dizinin öğe türü tüm öğeleri tarafından [desteklenen tüm unsurları](xref:microsoft.quantum.guide.operationsfunctions) destekler.</span><span class="sxs-lookup"><span data-stu-id="c1866-311">The element type of the array supports any [functors](xref:microsoft.quantum.guide.operationsfunctions) that are supported by all of the elements.</span></span>
<span data-ttu-id="c1866-312">Örneğin,, `Op1` `Op2` ve `Op3` hepsi `Qubit[] => Unit` operasyonlardır, ancak `Op1` `Adjoint` `Op2` her ikisini de destekler, destekler `Controlled` ve `Op3` destekler:</span><span class="sxs-lookup"><span data-stu-id="c1866-312">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit` operations, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>
  * <span data-ttu-id="c1866-313">`[Op1, Op2]`, bir dizi `(Qubit[] => Unit)` işlemden oluşur.</span><span class="sxs-lookup"><span data-stu-id="c1866-313">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
  * <span data-ttu-id="c1866-314">`[Op1, Op3]`, bir dizi `(Qubit[] => Unit is Adj)` işlemden oluşur.</span><span class="sxs-lookup"><span data-stu-id="c1866-314">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
  * <span data-ttu-id="c1866-315">`[Op2, Op3]`, bir dizi `(Qubit[] => Unit is Ctl)` işlemden oluşur.</span><span class="sxs-lookup"><span data-stu-id="c1866-315">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="c1866-316">Ancak, işlemler `(Qubit[] => Unit is Adj)` ve `(Qubit[] => Unit is Ctl)` ortak temel türüne sahip olmakla birlikte `(Qubit[] => Unit)` , bu işlemlerin *dizileri* ortak bir temel türü paylaşmazlar.</span><span class="sxs-lookup"><span data-stu-id="c1866-316">However, while the operations `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` have the common base type of `(Qubit[] => Unit)`, *arrays* of these operations do not share a common base type.</span></span>

<span data-ttu-id="c1866-317">Örneğin, `[[Op1], [Op2]]` Şu anda iki uyumsuz dizi türünden oluşan bir dizi oluşturmayı denediğinde bir hata oluşturur `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-317">For example, `[[Op1], [Op2]]` would currently raise an error because it attempts to create an array of the two incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>

<span data-ttu-id="c1866-318">Callables hakkında daha fazla bilgi için bu sayfadaki veya [işlemler ve Q# işlevlerde ](xref:microsoft.quantum.guide.operationsfunctions) [çağrılabilir ifadeler](#callable-expressions) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="c1866-318">For more information on callables, see [Callable expressions](#callable-expressions)  on this page or [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="c1866-319">Koşullu Ifadeler</span><span class="sxs-lookup"><span data-stu-id="c1866-319">Conditional Expressions</span></span>

<span data-ttu-id="c1866-320">Aynı türde ve bir Boolean ifadesinin iki ifadesi verildiğinde, soru işaretini, ve dikey çubuğu kullanarak koşullu bir ifade oluşturur `?` `|` .</span><span class="sxs-lookup"><span data-stu-id="c1866-320">Given two expressions of the same type and a Boolean expression, form a conditional expression using the question mark, `?`, and the vertical bar `|`.</span></span> <span data-ttu-id="c1866-321">Verildiğinde `a==b ? c | d` , koşullu ifadenin değeri `c` `a==b` true ise ve false ise `d` .</span><span class="sxs-lookup"><span data-stu-id="c1866-321">Given `a==b ? c | d`, the value of the conditional expression is `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="c1866-322">Callables ile koşullu ifadeler</span><span class="sxs-lookup"><span data-stu-id="c1866-322">Conditional expressions with callables</span></span>

<span data-ttu-id="c1866-323">Koşullu ifadeler, aynı girişlere ve çıkışlara sahip olan ancak farklı komik desteği olan işlemleri değerlendirebilir.</span><span class="sxs-lookup"><span data-stu-id="c1866-323">Conditional expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span> <span data-ttu-id="c1866-324">Bu durumda, koşullu ifadenin türü, her iki ifade tarafından desteklenen tüm semantikleri destekleyen giriş ve çıkışlarla bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-324">In this case, the type of the conditional expression is an operation with inputs and outputs that support any functors supported by both expressions.</span></span>
<span data-ttu-id="c1866-325">Örneğin,, ve hepsi ise,, `Op1` `Op2` ve `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` her ikisini de destekler, destekler ve `Op3` destekler:</span><span class="sxs-lookup"><span data-stu-id="c1866-325">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="c1866-326">`flag ? Op1 | Op2`bir `(Qubit[] => Unit)` işlemdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-326">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="c1866-327">`flag ? Op1 | Op3`bir `(Qubit[] => Unit is Adj)` işlemdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-327">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="c1866-328">`flag ? Op2 | Op3`bir `(Qubit[] => Unit is Ctl)` işlemdir.</span><span class="sxs-lookup"><span data-stu-id="c1866-328">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="c1866-329">Olası iki sonuç ifadesinin herhangi biri bir işlev veya işlem çağrısını içeriyorsa, bu çağrı yalnızca çağrının değeri olan bir sonuç olduğunda gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="c1866-329">If either of the two possible result expressions include a function or operation call, that call only takes place if that result is the one that is the value of the call.</span></span> <span data-ttu-id="c1866-330">Örneğin, bu durumda, `a==b ? C(qs) | D(qs)` `a==b` true ise `C` işlem çağrılır ve yanlış ise yalnızca `D` işlem çağrılır.</span><span class="sxs-lookup"><span data-stu-id="c1866-330">For example, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true, then the `C` operation is invoked, and if it is false then only the `D` operation is invoked.</span></span> <span data-ttu-id="c1866-331">Bu yaklaşım, diğer dillerdeki *kısa* devre 'ya benzer.</span><span class="sxs-lookup"><span data-stu-id="c1866-331">This approach is similar to *short-circuiting* in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="c1866-332">Çağrılabilir Ifadeler</span><span class="sxs-lookup"><span data-stu-id="c1866-332">Callable Expressions</span></span>

<span data-ttu-id="c1866-333">Çağrılabilir sabit değer, derleme kapsamında tanımlanan bir işlemin veya işlevin adıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-333">A callable literal is the name of an operation or function defined in the compilation scope.</span></span> <span data-ttu-id="c1866-334">Örneğin, `X` standart kitaplık işlemine başvuran bir işlem sabit değeri `X` ve `Message` standart kitaplık işlevine başvuran bir işlev sabit değeri `Message` .</span><span class="sxs-lookup"><span data-stu-id="c1866-334">For example, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="c1866-335">Bir işlem `Adjoint` functor destekliyorsa, `Adjoint op` bir işlem ifadesi olur.</span><span class="sxs-lookup"><span data-stu-id="c1866-335">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="c1866-336">Benzer şekilde, işlem `Controlled` functor 'ı destekliyorsa, `Controlled op` bir işlem ifadesi olur.</span><span class="sxs-lookup"><span data-stu-id="c1866-336">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="c1866-337">Bu ifadelerin türleri hakkında daha fazla bilgi için bkz. [işlem uzmanlıklarını çağırma](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span><span class="sxs-lookup"><span data-stu-id="c1866-337">For more information about the types of these expressions, see [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="c1866-338">Funörler ( `Adjoint` ve `Controlled` ), ile geri sarım operatörü `!` ve dizi dizini oluşturma dışında diğer işleçlerden daha yakından bağlanır `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="c1866-338">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[ ]`.</span></span>
<span data-ttu-id="c1866-339">Bu nedenle, işlemlerin kullanılan funları destekledikleri varsayılarak aşağıdakiler geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="c1866-339">Thus, the following are all valid, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="c1866-340">Tür parametreli çağrılabilir ifadeler</span><span class="sxs-lookup"><span data-stu-id="c1866-340">Type-parameterized callable expressions</span></span>

<span data-ttu-id="c1866-341">Çağrılabilir bir sabit değeri, örneğin, bir değişkene atamak veya başka bir çağrılabilir öğesine geçirmek için değer olarak kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-341">You can use a callable literal as a value, for example, to assign it to a variable or pass it to another callable.</span></span> <span data-ttu-id="c1866-342">Bu durumda, çağrılabilir [tür parametrelerine](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)sahipse, çağrılabilir değerin parçası olarak parametreleri sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="c1866-342">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), you must provide the parameters as part of the callable value.</span></span>

<span data-ttu-id="c1866-343">Çağrılabilir bir değer belirtilmeyen tür parametrelerine sahip olamaz.</span><span class="sxs-lookup"><span data-stu-id="c1866-343">A callable value cannot have any unspecified type parameters.</span></span> <span data-ttu-id="c1866-344">Örneğin, `Fun` imzaya sahip bir işlevdir `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="c1866-344">For example, if `Fun` is a function with the signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomeOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="c1866-345">Çağrılabilir çağırma Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="c1866-345">Callable Invocation Expressions</span></span>

<span data-ttu-id="c1866-346">Çağrılabilir bir ifade (işlem veya işlev) ve çağrılabilir öğesinin giriş türünün bir tanımlama grubu ifadesi verildiğinde, çağrılabilir ifadeye demet ifadesini ekleyerek bir *çağırma ifadesi* oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-346">Given a callable expression (operation or function) and a tuple expression of the input type of the callable's signature, you can form an *invocation expression* by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="c1866-347">Çağırma ifadesinin türü, çağrılabilir olan imzanın çıkış türüdür.</span><span class="sxs-lookup"><span data-stu-id="c1866-347">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="c1866-348">Örneğin, `Op` imzaya sahip bir işlem ise `((Int, Qubit) => Double)` , `Op(3, qubit1)` türünde bir ifadedir `Double` .</span><span class="sxs-lookup"><span data-stu-id="c1866-348">For example, if `Op` is an operation with the signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="c1866-349">Benzer şekilde, `Sin` imzaya sahip bir `(Double -> Double)` `Sin(0.1)` işlevsiyse, türünde bir ifadedir `Double` .</span><span class="sxs-lookup"><span data-stu-id="c1866-349">Similarly, if `Sin` is a function with the signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="c1866-350">Son olarak, `Builder` imzaya sahip bir işlevle `(Int -> (Int -> Int))` , ' `Builder(3)` den ' a bir işlevdir `Int` `Int` .</span><span class="sxs-lookup"><span data-stu-id="c1866-350">Finally, if `Builder` is a function with the signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from `Int` to `Int`.</span></span>

<span data-ttu-id="c1866-351">Çağrılabilir değerli bir ifadenin sonucunu çağırmak, çağrılabilir ifade etrafında fazladan bir çift parantez gerektirir.</span><span class="sxs-lookup"><span data-stu-id="c1866-351">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="c1866-352">Bu nedenle, önceki paragraftan çağırma sonucunu çağırmak için `Builder` doğru sözdizimi şöyledir:</span><span class="sxs-lookup"><span data-stu-id="c1866-352">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="c1866-353">Bir [tür parametreli](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) çağrılabilir çağırılırken, çağrılabilir ifadeden sonra, açılı ayraç içinde gerçek tür parametrelerini belirtebilirsiniz `< >` .</span><span class="sxs-lookup"><span data-stu-id="c1866-353">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, you can specify the actual type parameters within angle brackets `< >` after the callable expression.</span></span>
<span data-ttu-id="c1866-354">Derleyici gerçek türleri olduğu için bu eylem genellikle gereksizdir Q# .</span><span class="sxs-lookup"><span data-stu-id="c1866-354">This action is usually unnecessary as the Q# compiler infers the actual types.</span></span>
<span data-ttu-id="c1866-355">Ancak, tür parametreli bir bağımsız değişken belirtilmemişse, [kısmi uygulama](xref:microsoft.quantum.guide.operationsfunctions#partial-application) *için gereklidir.*</span><span class="sxs-lookup"><span data-stu-id="c1866-355">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="c1866-356">Aynı zamanda farklı bir functor ile işlemleri bir çağrılabilir hale geçirilerek de yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="c1866-356">It is also useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="c1866-357">Örneğin, imzası varsa `Func` `('T1, 'T2, 'T1) -> 'T2` `Op1` ve `Op2` imza içeriyorsa `(Qubit[] => Unit is Adj)` ve `Op3` `(Qubit[] => Unit)` `Func` `Op1` ilk bağımsız değişken olarak, `Op2` ikinci olarak ve `Op3` Üçüncü olarak çağırmak için imza varsa:</span><span class="sxs-lookup"><span data-stu-id="c1866-357">For example, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="c1866-358">Tür belirtimi gereklidir çünkü `Op3` ve `Op1` farklı türlere sahip olur, bu nedenle derleyici bunu belirtim olmadan belirsiz olarak değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="c1866-358">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="c1866-359">İşleç Önceliği</span><span class="sxs-lookup"><span data-stu-id="c1866-359">Operator Precedence</span></span>

* <span data-ttu-id="c1866-360">Tüm ikili işleçler, hariç olmak üzere, doğru ilişkilendirilebilir `^` .</span><span class="sxs-lookup"><span data-stu-id="c1866-360">All binary operators are right-associative, except for `^`.</span></span>

* <span data-ttu-id="c1866-361">Parantez, `[ ]` dizi Dilimleme ve dizin oluşturma için herhangi bir işleçten önce bağlayın.</span><span class="sxs-lookup"><span data-stu-id="c1866-361">Brackets, `[ ]`, for array slicing and indexing, bind before any operator.</span></span>

* <span data-ttu-id="c1866-362">`Adjoint`Ve `Controlled` diğer tüm işleçlerden önce, dizi dizinlemesi ve sonra bağlama.</span><span class="sxs-lookup"><span data-stu-id="c1866-362">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

* <span data-ttu-id="c1866-363">İşlem ve işlev çağırma parantezleri aynı zamanda herhangi bir işleçten önce, ancak dizi dizinlemesi ve komik bir şekilde bağlanır.</span><span class="sxs-lookup"><span data-stu-id="c1866-363">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="c1866-364">Q#en yüksekten en düşüğe göre öncelik sırasına göre işleçler:</span><span class="sxs-lookup"><span data-stu-id="c1866-364">Q# operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="c1866-365">İşleç</span><span class="sxs-lookup"><span data-stu-id="c1866-365">Operator</span></span> | <span data-ttu-id="c1866-366">Sayısına</span><span class="sxs-lookup"><span data-stu-id="c1866-366">Arity</span></span> | <span data-ttu-id="c1866-367">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c1866-367">Description</span></span> | <span data-ttu-id="c1866-368">İşlenen türleri</span><span class="sxs-lookup"><span data-stu-id="c1866-368">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="c1866-369">arkasında`!`</span><span class="sxs-lookup"><span data-stu-id="c1866-369">trailing `!`</span></span> | <span data-ttu-id="c1866-370">Birli</span><span class="sxs-lookup"><span data-stu-id="c1866-370">Unary</span></span> | <span data-ttu-id="c1866-371">Unwrap</span><span class="sxs-lookup"><span data-stu-id="c1866-371">Unwrap</span></span> | <span data-ttu-id="c1866-372">Kullanıcı tanımlı herhangi bir tür</span><span class="sxs-lookup"><span data-stu-id="c1866-372">Any user-defined type</span></span>
 <span data-ttu-id="c1866-373">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="c1866-373">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="c1866-374">Birli</span><span class="sxs-lookup"><span data-stu-id="c1866-374">Unary</span></span> | <span data-ttu-id="c1866-375">Sayısal negatif, bit düzeyinde tamamlama, mantıksal değilleme</span><span class="sxs-lookup"><span data-stu-id="c1866-375">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="c1866-376">`Int`, için `BigInt` veya için `Double` `-` `Int` veya `BigInt` `~~~` `Bool` için`not`</span><span class="sxs-lookup"><span data-stu-id="c1866-376">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="c1866-377">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-377">Binary</span></span> | <span data-ttu-id="c1866-378">Tamsayı güç</span><span class="sxs-lookup"><span data-stu-id="c1866-378">Integer power</span></span> | <span data-ttu-id="c1866-379">`Int`üs için veya `BigInt` taban için `Int`</span><span class="sxs-lookup"><span data-stu-id="c1866-379">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="c1866-380">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="c1866-380">`/`, `*`, `%`</span></span> | <span data-ttu-id="c1866-381">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-381">Binary</span></span> | <span data-ttu-id="c1866-382">Bölme, çarpma, tamsayı mod</span><span class="sxs-lookup"><span data-stu-id="c1866-382">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="c1866-383">`Int`, `BigInt` veya `Double` için `/` `*` `Int` veya `BigInt` için`%`</span><span class="sxs-lookup"><span data-stu-id="c1866-383">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="c1866-384">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="c1866-384">`+`, `-`</span></span> | <span data-ttu-id="c1866-385">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-385">Binary</span></span> | <span data-ttu-id="c1866-386">Ekleme veya dize ve dizi birleştirme, çıkarma</span><span class="sxs-lookup"><span data-stu-id="c1866-386">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="c1866-387">`Int``BigInt`veya `Double` `String` için bir dizi türü veya`+`</span><span class="sxs-lookup"><span data-stu-id="c1866-387">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="c1866-388">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="c1866-388">`<<<`, `>>>`</span></span> | <span data-ttu-id="c1866-389">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-389">Binary</span></span> | <span data-ttu-id="c1866-390">Sol SHIFT, sağa kaydırma</span><span class="sxs-lookup"><span data-stu-id="c1866-390">Left shift, right shift</span></span> | <span data-ttu-id="c1866-391">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="c1866-391">`Int` or `BigInt`</span></span>
 <span data-ttu-id="c1866-392">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="c1866-392">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="c1866-393">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-393">Binary</span></span> | <span data-ttu-id="c1866-394">Küçüktür, küçüktür veya eşittir, büyüktür, büyüktür veya eşittir karşılaştırmaları</span><span class="sxs-lookup"><span data-stu-id="c1866-394">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="c1866-395">`Int``BigInt`veya`Double`</span><span class="sxs-lookup"><span data-stu-id="c1866-395">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="c1866-396">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="c1866-396">`==`, `!=`</span></span> | <span data-ttu-id="c1866-397">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-397">Binary</span></span> | <span data-ttu-id="c1866-398">eşit, eşit olmayan karşılaştırmalar</span><span class="sxs-lookup"><span data-stu-id="c1866-398">equal, not-equal comparisons</span></span> | <span data-ttu-id="c1866-399">herhangi bir ilkel tür</span><span class="sxs-lookup"><span data-stu-id="c1866-399">any primitive type</span></span>
 `&&&` | <span data-ttu-id="c1866-400">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-400">Binary</span></span> | <span data-ttu-id="c1866-401">Bit düzeyinde AND</span><span class="sxs-lookup"><span data-stu-id="c1866-401">Bitwise AND</span></span> | <span data-ttu-id="c1866-402">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="c1866-402">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="c1866-403">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-403">Binary</span></span> | <span data-ttu-id="c1866-404">Bit düzeyinde XOR</span><span class="sxs-lookup"><span data-stu-id="c1866-404">Bitwise XOR</span></span> | <span data-ttu-id="c1866-405">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="c1866-405">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="c1866-406">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-406">Binary</span></span> | <span data-ttu-id="c1866-407">Bit düzeyinde OR</span><span class="sxs-lookup"><span data-stu-id="c1866-407">Bitwise OR</span></span> | <span data-ttu-id="c1866-408">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="c1866-408">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="c1866-409">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-409">Binary</span></span> | <span data-ttu-id="c1866-410">Mantıksal VE</span><span class="sxs-lookup"><span data-stu-id="c1866-410">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="c1866-411">İkili</span><span class="sxs-lookup"><span data-stu-id="c1866-411">Binary</span></span> | <span data-ttu-id="c1866-412">Mantıksal EĞER</span><span class="sxs-lookup"><span data-stu-id="c1866-412">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="c1866-413">İkili/üçlü</span><span class="sxs-lookup"><span data-stu-id="c1866-413">Binary/Ternary</span></span> | <span data-ttu-id="c1866-414">Range işleci</span><span class="sxs-lookup"><span data-stu-id="c1866-414">Range operator</span></span> | `Int`
 <span data-ttu-id="c1866-415">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="c1866-415">`?` `|`</span></span> | <span data-ttu-id="c1866-416">Üçlü</span><span class="sxs-lookup"><span data-stu-id="c1866-416">Ternary</span></span> | <span data-ttu-id="c1866-417">Koşullu</span><span class="sxs-lookup"><span data-stu-id="c1866-417">Conditional</span></span> | <span data-ttu-id="c1866-418">`Bool`Sol taraftaki</span><span class="sxs-lookup"><span data-stu-id="c1866-418">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="c1866-419">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="c1866-419">`w/` `<-`</span></span> | <span data-ttu-id="c1866-420">Üçlü</span><span class="sxs-lookup"><span data-stu-id="c1866-420">Ternary</span></span> | <span data-ttu-id="c1866-421">Kopyala ve Güncelleştir</span><span class="sxs-lookup"><span data-stu-id="c1866-421">Copy-and-update</span></span> | <span data-ttu-id="c1866-422">Bkz. [kopyalama ve güncelleştirme ifadeleri](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="c1866-422">See [Copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1866-423">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="c1866-423">Next steps</span></span>

<span data-ttu-id="c1866-424">Artık içindeki ifadelerle Q# çalışacağınızı, işlemler ve işlevlerin nasıl tanımlanacağını ve çağrılacağını öğrenmek için [içindeki Q# işlemlere ve işlevlerine](xref:microsoft.quantum.guide.operationsfunctions) geçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c1866-424">Now that you can work with expressions in Q#, move on to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
