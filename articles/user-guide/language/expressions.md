---
title: 'Q içindeki tür Ifadeleri #'
description: Sabitleri, değişkenleri, işleçleri, işlemleri ve işlevleri soru-cevap olarak ifade olarak belirtme, başvurma ve birleştirme hakkında bilgi edinin.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: b32644382bb88fb11da00d0d7d78bbd797a0eaaa
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84629991"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="6c631-103">Q içindeki tür Ifadeleri #</span><span class="sxs-lookup"><span data-stu-id="6c631-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="6c631-104">Sayısal Ifadeler</span><span class="sxs-lookup"><span data-stu-id="6c631-104">Numeric Expressions</span></span>

<span data-ttu-id="6c631-105">Sayısal ifadeler `Int` , veya türündeki ifadelerdir `BigInt` `Double` .</span><span class="sxs-lookup"><span data-stu-id="6c631-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="6c631-106">Diğer bir deyişle, tamsayı veya kayan noktalı sayılardır.</span><span class="sxs-lookup"><span data-stu-id="6c631-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="6c631-107">`Int`Q # içindeki sabit değerler yalnızca bir dizi basamakla yazılır.</span><span class="sxs-lookup"><span data-stu-id="6c631-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="6c631-108">Onaltılık ve ikili tamsayılar `0x` `0b` sırasıyla ve önekiyle desteklenir.</span><span class="sxs-lookup"><span data-stu-id="6c631-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="6c631-109">`BigInt`Q # içindeki sabit değerler, sondaki `l` veya `L` son ek ile yazılır.</span><span class="sxs-lookup"><span data-stu-id="6c631-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="6c631-110">Onaltılık büyük tamsayılar bir "0x" öneki ile desteklenir.</span><span class="sxs-lookup"><span data-stu-id="6c631-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="6c631-111">Bu nedenle, tüm geçerli sabit değer kullanımları aşağıda verilmiştir `BigInt` :</span><span class="sxs-lookup"><span data-stu-id="6c631-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="6c631-112">`Double`Q # içindeki sabit değerler, ondalık basamaklar kullanılarak yazılan kayan nokta sayılarıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="6c631-113">Bunlar, bir ondalık noktayla, `.` ve/veya ' e ' veya ' e ' ile belirtilen üstel bir bölüm (yalnızca olası bir negatif işaret ve ondalık basamakların geçerli olması) ile yazılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="6c631-114">Aşağıdakiler geçerli `Double` değişmez değerler: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="6c631-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="6c631-115">Herhangi bir öğe türünün dizi ifadesi verildiğinde, bir `Int` ifade [`Length`](xref:microsoft.quantum.core.length) yerleşik işlev kullanılarak, dizi ifadesi parantez içine alınmış ve ile oluşturulmuş olabilir `(` `)` .</span><span class="sxs-lookup"><span data-stu-id="6c631-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="6c631-116">Örneğin, `a` bir diziye bağlıysa, bir `Length(a)` tamsayı ifadesidir.</span><span class="sxs-lookup"><span data-stu-id="6c631-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="6c631-117">, `b` Tamsayıların dizilerindeki bir diziyse, `Int[][]` `Length(b)` içindeki alt dizilerin sayısıdır `b` ve `Length(b[1])` içindeki ikinci alt dizideki tamsayıların sayısıdır `b` .</span><span class="sxs-lookup"><span data-stu-id="6c631-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="6c631-118">Aynı türde iki sayısal ifade verildiğinde, ikili işleçler,,, `+` `-` `*` ve `/` Yeni bir sayısal ifade oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="6c631-119">Yeni ifadenin türü, bileşen ifadelerinin türleriyle aynı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="6c631-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="6c631-120">İki tamsayı ifadesi verildiğinde, ikili işleç `^` (güç) yeni bir tamsayı ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="6c631-121">Benzer şekilde, `^` Yeni bir Double ifadesi oluşturmak için iki çift ifade ile birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="6c631-122">Son olarak, `^` solda büyük bir tamsayı ve yeni bir büyük tamsayı ifadesi oluşturmak için sağdaki bir tamsayı ile birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="6c631-123">Bu durumda, ikinci parametrenin 32 bite sığması gerekir; Aksi takdirde, bir çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="6c631-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="6c631-124">İki tamsayı veya büyük tamsayı ifadesi verildiğinde, `%` (mod), `&&&` (BIT düzeyinde and), `|||` (bit düzeyinde OR) veya `^^^` (bit düzeyinde xor) işleçleri kullanılarak yeni bir tamsayı veya büyük tamsayı ifadesi oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="6c631-125">Sol tarafta bir tamsayı veya büyük tamsayı ifadesi ve sağ taraftaki bir tamsayı ifadesi verildiğinde, `<<<` (aritmetik sol SHIFT) veya `>>>` (aritmetik sağa kaydırma) işleçleri, sol ifadeyle aynı türde yeni bir ifade oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="6c631-126">Kaydırma işleminin ikinci parametresi (SHIFT miktarı) sıfırdan büyük veya sıfıra eşit olmalıdır; negatif kaydırma miktarları için davranış tanımsızdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="6c631-127">Her iki vardiya işlemi için de SHIFT miktarı 32 bite uyum sağlamalıdır; Aksi takdirde, bir çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="6c631-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="6c631-128">Kaydırılan sayı bir tamsayı ise, SHIFT miktarı yorumlanır `mod 64` ; Yani, 1 vardiyası ve 65 vardiyası aynı etkiye sahiptir.</span><span class="sxs-lookup"><span data-stu-id="6c631-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="6c631-129">Hem tamsayı hem de büyük tamsayı değerleri için, vardiyalar aritmetik değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="6c631-130">Negatif bir değeri sol veya sağ kaydırma, negatif bir sayı ile sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="6c631-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="6c631-131">Diğer bir deyişle, bir adım sola veya sağa kaydırma, sırasıyla 2 ile çarpılarak veya bölünerek tamamen aynıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="6c631-132">Tamsayı bölme ve tamsayı mod, negatif sayılar için C# olarak aynı davranışı izler.</span><span class="sxs-lookup"><span data-stu-id="6c631-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="6c631-133">Diğer bir deyişle, `a % b` her zaman aynı işarete sahip olur `a` ve `b * (a / b) + a % b` her zaman eşit olur `a` .</span><span class="sxs-lookup"><span data-stu-id="6c631-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="6c631-134">Örnek:</span><span class="sxs-lookup"><span data-stu-id="6c631-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="6c631-135">5</span><span class="sxs-lookup"><span data-stu-id="6c631-135">5</span></span> | <span data-ttu-id="6c631-136">2</span><span class="sxs-lookup"><span data-stu-id="6c631-136">2</span></span> | <span data-ttu-id="6c631-137">2</span><span class="sxs-lookup"><span data-stu-id="6c631-137">2</span></span> | <span data-ttu-id="6c631-138">1</span><span class="sxs-lookup"><span data-stu-id="6c631-138">1</span></span>
 <span data-ttu-id="6c631-139">5</span><span class="sxs-lookup"><span data-stu-id="6c631-139">5</span></span> | <span data-ttu-id="6c631-140">-2</span><span class="sxs-lookup"><span data-stu-id="6c631-140">-2</span></span> | <span data-ttu-id="6c631-141">-2</span><span class="sxs-lookup"><span data-stu-id="6c631-141">-2</span></span> | <span data-ttu-id="6c631-142">1</span><span class="sxs-lookup"><span data-stu-id="6c631-142">1</span></span>
 <span data-ttu-id="6c631-143">-5</span><span class="sxs-lookup"><span data-stu-id="6c631-143">-5</span></span> | <span data-ttu-id="6c631-144">2</span><span class="sxs-lookup"><span data-stu-id="6c631-144">2</span></span> | <span data-ttu-id="6c631-145">-2</span><span class="sxs-lookup"><span data-stu-id="6c631-145">-2</span></span> | <span data-ttu-id="6c631-146">-1</span><span class="sxs-lookup"><span data-stu-id="6c631-146">-1</span></span>
 <span data-ttu-id="6c631-147">-5</span><span class="sxs-lookup"><span data-stu-id="6c631-147">-5</span></span> | <span data-ttu-id="6c631-148">-2</span><span class="sxs-lookup"><span data-stu-id="6c631-148">-2</span></span> | <span data-ttu-id="6c631-149">2</span><span class="sxs-lookup"><span data-stu-id="6c631-149">2</span></span> | <span data-ttu-id="6c631-150">-1</span><span class="sxs-lookup"><span data-stu-id="6c631-150">-1</span></span>

<span data-ttu-id="6c631-151">Büyük tamsayı bölme ve mod aynı şekilde çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="6c631-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="6c631-152">Herhangi bir sayısal ifade verildiğinde, birli işleç kullanılarak yeni bir ifade oluşturulmuş olabilir `-` .</span><span class="sxs-lookup"><span data-stu-id="6c631-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="6c631-153">Yeni ifade, anayent ifadesiyle aynı türde olacaktır.</span><span class="sxs-lookup"><span data-stu-id="6c631-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="6c631-154">Herhangi bir tamsayı veya büyük tamsayı ifadesi verildiğinde, aynı türde yeni bir ifade `~~~` (bit düzeyinde tamamlayıcı) birli işleç kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="6c631-155">Boole İfadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-155">Boolean Expressions</span></span>

<span data-ttu-id="6c631-156">İki `Bool` değişmez değer de `true` ve ' dir `false` .</span><span class="sxs-lookup"><span data-stu-id="6c631-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="6c631-157">Aynı ilkel türdeki iki ifade verildiğinde, `==` ve `!=` ikili işleçler bir ifade oluşturmak için kullanılabilir `Bool` .</span><span class="sxs-lookup"><span data-stu-id="6c631-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="6c631-158">İki ifade eşitse ifade true, değilse false olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="6c631-159">Kullanıcı tanımlı türlerin değerleri karşılaştırılamayabilir, yalnızca sarmalanmamış değerler karşılaştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="6c631-160">Örneğin, "sarmalama" işlecini kullanma `!` ( [Q # türlerinde](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)ayrıntılı olarak açıklanmıştır),</span><span class="sxs-lookup"><span data-stu-id="6c631-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="6c631-161">Değerler için eşitlik karşılaştırması `Qubit` kimlik eşitlik, yani iki ifadenin aynı qubit 'i tanımlamasına bakılmaksızın.</span><span class="sxs-lookup"><span data-stu-id="6c631-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="6c631-162">İki qubits 'in durumu karşılaştırılmaz, erişilmez, ölçülemez veya bu karşılaştırma tarafından değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="6c631-163">Değerler için eşitlik karşılaştırması `Double` , yuvarlama etkileri nedeniyle yanıltıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="6c631-164">Örneğin, `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="6c631-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="6c631-165">Herhangi iki sayısal ifade verildiğinde,,, ve ikili işleçleri,,, `>` `<` `>=` ve `<=` ilk ifade sırasıyla sıfırdan büyük, küçüktür, büyüktür veya eşittir veya ikinci ifadeden daha küçük veya eşit olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="6c631-166">İki Boolean ifade verildiğinde, `and` ve `or` ikili işleçler, iki ifadenin her ikisi de (her ikisi de veya her ikisi de) doğru olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="6c631-167">Herhangi bir Boole ifadesi verildiğinde, `not` birli işleç yanlış olduğunda, doğru olan yeni bir Boole ifadesi oluşturmak için birli işleç kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="6c631-168">Dize Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-168">String Expressions</span></span>

<span data-ttu-id="6c631-169">Q #, `fail` deyimde ( [Denetim akışında](xref:microsoft.quantum.guide.controlflow#fail-statement)açıklanmıştır) ve standart işlevde dizelerin kullanılmasına izin verir [`Message`](xref:microsoft.quantum.intrinsic.message) .</span><span class="sxs-lookup"><span data-stu-id="6c631-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="6c631-170">İkinci öğesinin belirli davranışı kullanılan simülatmaya bağlıdır, ancak genellikle bir Q # programı sırasında çağrıldığında ana bilgisayar konsoluna bir ileti yazar.</span><span class="sxs-lookup"><span data-stu-id="6c631-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="6c631-171">Q # içindeki dizeler, değişmez değer veya enterpolasyonlu dizelerdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="6c631-172">Dize sabit değerleri çoğu dilde basit dize sabit değerlerine benzer: çift tırnak içine alınmış bir Unicode karakter dizisi `"` .</span><span class="sxs-lookup"><span data-stu-id="6c631-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="6c631-173">Bir dizenin içinde, arka eğik çizgi karakteri `\` bir çift tırnak karakteriyle çıkmak ve yeni satır `\n` , satır başı olarak `\r` ve bir sekme olarak eklemek için kullanılabilir `\t` .</span><span class="sxs-lookup"><span data-stu-id="6c631-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="6c631-174">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="6c631-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="6c631-175">Ara değerli dizeler</span><span class="sxs-lookup"><span data-stu-id="6c631-175">Interpolated strings</span></span>

<span data-ttu-id="6c631-176">Dize enterpolasyonları için Q # sözdizimi, C# sözdiziminin bir alt kümesidir, ancak burada soru-cevap ' a ait olan anahtar noktalarını özetliyoruz.</span><span class="sxs-lookup"><span data-stu-id="6c631-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="6c631-177">Ana farklılıklar aşağıda ele alınmıştır.</span><span class="sxs-lookup"><span data-stu-id="6c631-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="6c631-178">Bir dize sabit değerini, enterpolasyonlu bir dize olarak tanımlamak için, `$` simgeyi simgesiyle önüne ekleyin.</span><span class="sxs-lookup"><span data-stu-id="6c631-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="6c631-179">`$`Ve arasında `"` bir dize sabiti Başlatan boşluk olamaz.</span><span class="sxs-lookup"><span data-stu-id="6c631-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="6c631-180">Aşağıdaki, [`Message`](xref:microsoft.quantum.intrinsic.message) diğer Q # ifadeleriyle birlikte, bir ölçünün sonucunu konsola yazmak için işlevi kullanan temel bir örnektir.</span><span class="sxs-lookup"><span data-stu-id="6c631-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="6c631-181">Geçerli bir Q # ifadesi, enterpolasyonlu bir dizede görünebilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="6c631-182">C# sözdizimi hakkında daha fazla ayrıntı, [*enterpolasyonlu dizelerde*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings)bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="6c631-183">En önemli ayrım, Q # ' ın tam (çok satırlı) enterpolasyonlu dizeleri desteklemedir.</span><span class="sxs-lookup"><span data-stu-id="6c631-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="6c631-184">Enterpolasyonlu dize içindeki ifadeler, C# söz dizimini değil, Q # söz dizimini izler.</span><span class="sxs-lookup"><span data-stu-id="6c631-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="6c631-185">Aralık Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-185">Range Expressions</span></span>

<span data-ttu-id="6c631-186">, Ve olmak üzere üç ifade verildiğinde, `Int` `start` `step` `stop` `start .. step .. stop` birinci öğesi olan bir Aralık ifadesi, `start` ikinci öğe ise, `start+step` üçüncü öğe, `start+step+step` vb. olur `stop` .</span><span class="sxs-lookup"><span data-stu-id="6c631-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="6c631-187">Örneğin, pozitif ve olduğunda bir Aralık boş olabilir `step` `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="6c631-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="6c631-188">Aralığın son öğesi, `stop` ve arasındaki fark, ve arasındaki fark olur `start` `stop` `step` ; diğer bir deyişle, Aralık her iki uçta da dahil olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="6c631-189">Her iki ifade de verildiğinde `Int` `start` `stop` , ve `start .. stop` değerine eşit bir Aralık deyimidir `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="6c631-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="6c631-190">Önünde ve `step` ' den küçük olsa bile, örtük ' ın + 1 olduğunu unutmayın `stop` `start` . böyle bir durumda, Aralık boş olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="6c631-191">Bazı örnek aralıklar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="6c631-191">Some example ranges are:</span></span>

- <span data-ttu-id="6c631-192">`1..3`1, 2, 3 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="6c631-193">`2..2..5`2, 4 aralığındadır.</span><span class="sxs-lookup"><span data-stu-id="6c631-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="6c631-194">`2..2..6`2, 4, 6 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="6c631-195">`6..-2..2`6, 4, 2 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="6c631-196">`2..1`boş aralıktır.</span><span class="sxs-lookup"><span data-stu-id="6c631-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="6c631-197">`2..6..7`Aralık 2 ' dir.</span><span class="sxs-lookup"><span data-stu-id="6c631-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="6c631-198">`2..2..1`boş aralıktır.</span><span class="sxs-lookup"><span data-stu-id="6c631-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="6c631-199">`1..-1..2`boş aralıktır.</span><span class="sxs-lookup"><span data-stu-id="6c631-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="6c631-200">Qubit Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-200">Qubit Expressions</span></span>

<span data-ttu-id="6c631-201">Tek `Qubit` ifadeler, `Qubit` dizilerin değerlerine veya dizi öğelerine bağlanan sembollerdir `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="6c631-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="6c631-202">Değişmez değer yok `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="6c631-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="6c631-203">Pauli Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-203">Pauli Expressions</span></span>

<span data-ttu-id="6c631-204">Dört değeri,,, `Pauli` `PauliI` `PauliX` `PauliY` ve `PauliZ` , tüm geçerli `Pauli` ifadelerdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="6c631-205">Bunun dışında, tek ifadeler, `Pauli` `Pauli` dizilere ait değerlere veya dizi öğelerine bağlanan sembollerdir `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="6c631-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="6c631-206">Sonuç Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-206">Result Expressions</span></span>

<span data-ttu-id="6c631-207">İki `Result` değer `One` ve `Zero` , geçerli `Result` ifadelerdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="6c631-208">Bunun dışında, tek ifadeler, `Result` `Result` dizilere ait değerlere veya dizi öğelerine bağlanan sembollerdir `Result` .</span><span class="sxs-lookup"><span data-stu-id="6c631-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="6c631-209">Özellikle, `One` tamsayıyla aynı olmadığını ve aralarında doğrudan dönüşüm olmadığını unutmayın `1` .</span><span class="sxs-lookup"><span data-stu-id="6c631-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="6c631-210">Aynı, ve için de `Zero` geçerlidir `0` .</span><span class="sxs-lookup"><span data-stu-id="6c631-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="6c631-211">Demet Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-211">Tuple Expressions</span></span>

<span data-ttu-id="6c631-212">Tanımlama grubu değişmez değeri, ve ' de bulunan, virgülle ayrılmış şekilde, uygun türdeki öğe ifadelerinin dizelerdir `(` `)` .</span><span class="sxs-lookup"><span data-stu-id="6c631-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="6c631-213">Örneğin, `(1, One)` bir `(Int, Result)` ifadedir.</span><span class="sxs-lookup"><span data-stu-id="6c631-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="6c631-214">Değişmez değerler dışında, tek demet ifadeleri demet değerlerine, demet dizilerinin dizi öğelerine ve tanımlama grupları döndüren çağrılabilir çağırmaları olan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="6c631-215">Kullanıcı tanımlı tür Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="6c631-216">Kullanıcı tanımlı bir türün sabit değeri tür adından, ardından türün temel demet türünün bir tanımlama grubu değişmez değerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="6c631-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="6c631-217">Örneğin, `IntPair` temelli Kullanıcı tanımlı bir tür ise `(Int, Int)` , `IntPair(2, 3)` Bu türün geçerli bir sabit değeri olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="6c631-218">Değişmez değerler dışında, Kullanıcı tanımlı bir türün tek ifadeleri, bu türün değerlerine, bu türden dizilerin dizi öğelerine ve bu türü döndüren çağrılabilir çağırmaları olan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="6c631-219">Ifade kaydırmayı geri al</span><span class="sxs-lookup"><span data-stu-id="6c631-219">Unwrap Expressions</span></span>

<span data-ttu-id="6c631-220">Q # içinde, Unwrap işleci sondaki bir ünlem işaretidir `!` .</span><span class="sxs-lookup"><span data-stu-id="6c631-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="6c631-221">Örneğin, `IntPair` temel alınan türe sahip kullanıcı tanımlı bir türdür `(Int, Int)` ve `s` değeri olan bir değişkense, `IntPair(2, 3)` daha sonra `s!` olur `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="6c631-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="6c631-222">Diğer Kullanıcı tanımlı türler bakımından tanımlanan Kullanıcı tanımlı türler için, Unwrap işleci yinelenebilir. Örneğin, `s!!` paketlenmiş, sarmalanmamış değeri gösterir `s` .</span><span class="sxs-lookup"><span data-stu-id="6c631-222">For user-defined types defined in terms of other user-defined types, the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="6c631-223">Bu nedenle, `WrappedPair` temel alınan türe sahip kullanıcı tanımlı bir türdür `IntPair` ve `t` değeri olan bir değişkense, `WrappedPair(IntPair(1,2))` `t!!` olur `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="6c631-223">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="6c631-224">`!`İşleç, `[]` dizi dizini oluşturma ve dilimleme için dışındaki diğer işleçlerden daha yüksek önceliğe sahiptir.</span><span class="sxs-lookup"><span data-stu-id="6c631-224">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="6c631-225">`!``[]`, pozitif bir değer; yani, `a[i]![3]` şöyle okunmalıdır `((a[i])!)[3]` : `i` ' th öğesini al `a` , sarmalama kaldır ve sonra sarmalanmamış değerin 3. öğesini (bir dizi olması gerekir) alın.</span><span class="sxs-lookup"><span data-stu-id="6c631-225">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="6c631-226">`!`İşlecin önceliği belirgin olmayan bir etkiye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-226">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="6c631-227">Bir işlev veya işlem sarmalanmamış bir değer döndürürse, bağımsız değişken grubu, sarmalama yerine çağrıya bağlamak için işlev veya işlem çağrısının parantez içine alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="6c631-227">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="6c631-228">Örnek:</span><span class="sxs-lookup"><span data-stu-id="6c631-228">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="6c631-229">Dizi Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-229">Array Expressions</span></span>

<span data-ttu-id="6c631-230">Dizi değişmez değeri, virgülle ayrılmış bir veya daha fazla öğe ifadesinin sırasıdır `[` ve `]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-230">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="6c631-231">Tüm öğeler aynı türle uyumlu olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-231">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="6c631-232">Aynı türde iki dizi verildiğinde, ikili `+` işleç iki dizinin birleşimi olan yeni bir dizi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-232">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="6c631-233">Örneğin, `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-233">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="6c631-234">Dizi oluşturma</span><span class="sxs-lookup"><span data-stu-id="6c631-234">Array Creation</span></span>

<span data-ttu-id="6c631-235">Bir tür ve ifade verildiğinde `Int` , `new` işleç verilen boyutun yeni bir dizisini ayırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-235">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="6c631-236">Örneğin, `new Int[i + 1]` `Int` öğeleri içeren yeni bir dizi ayırır `i + 1` .</span><span class="sxs-lookup"><span data-stu-id="6c631-236">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="6c631-237">Boş dizi değişmez `[]` değerlerine izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="6c631-237">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="6c631-238">Bunun yerine `new ★[0]` ,, `★` uygun bir tür için yer tutucu olarak olduğu gibi, istenen sıfır uzunluklu diziyi oluşturulmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="6c631-238">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="6c631-239">Yeni bir dizinin öğeleri, türe bağlı bir varsayılan değere başlatılır.</span><span class="sxs-lookup"><span data-stu-id="6c631-239">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="6c631-240">Çoğu durumda bu bazı sıfır çeşitlerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="6c631-240">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="6c631-241">Varlıklara başvurular olan qubits ve callables için makul bir varsayılan değer yoktur.</span><span class="sxs-lookup"><span data-stu-id="6c631-241">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="6c631-242">Bu nedenle, bu tür için varsayılan, çalışma zamanı hatasına neden olmadan kullanılamayan geçersiz bir başvurudur.</span><span class="sxs-lookup"><span data-stu-id="6c631-242">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="6c631-243">Bu, C# veya Java gibi dillerde null başvuruya benzer.</span><span class="sxs-lookup"><span data-stu-id="6c631-243">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="6c631-244">Qubits veya callables içeren diziler, öğeleri güvenle kullanılmadan önce varsayılan olmayan değerlerle düzgün başlatılmış olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-244">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="6c631-245">İçin uygun başlatma yordamları bulunabilir <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="6c631-245">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="6c631-246">Her türün varsayılan değerleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="6c631-246">The default values for each type are:</span></span>

<span data-ttu-id="6c631-247">Tür</span><span class="sxs-lookup"><span data-stu-id="6c631-247">Type</span></span> | <span data-ttu-id="6c631-248">Varsayılan</span><span class="sxs-lookup"><span data-stu-id="6c631-248">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="6c631-249">_geçersiz qubit_</span><span class="sxs-lookup"><span data-stu-id="6c631-249">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="6c631-250">Boş Aralık,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="6c631-250">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="6c631-251">_geçersiz çağrılabilir_</span><span class="sxs-lookup"><span data-stu-id="6c631-251">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="6c631-252">Demet türleri, öğe öğesi tarafından başlatılmış.</span><span class="sxs-lookup"><span data-stu-id="6c631-252">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="6c631-253">Dizi öğeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-253">Array Elements</span></span>

<span data-ttu-id="6c631-254">Bir dizi ifadesi ve bir `Int` ifade verildiğinde, `[` ve dizi öğesi işleci kullanılarak yeni bir ifade oluşturulabilir `]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-254">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="6c631-255">Yeni ifade, dizinin öğe türüyle aynı türde olacaktır.</span><span class="sxs-lookup"><span data-stu-id="6c631-255">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="6c631-256">Örneğin, bir `a` dizi s öğesine bağlıysa, `Double` `a[4]` bir `Double` ifadedir.</span><span class="sxs-lookup"><span data-stu-id="6c631-256">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="6c631-257">Dizi ifadesi basit bir tanımlayıcı değilse, bir öğe seçmek için parantez içine alınmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-257">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="6c631-258">Örneğin, `a` ve `b` öğelerinin her ikisi de varsa `Int` , birleştirilmeden bir öğe şöyle ifade edilir:</span><span class="sxs-lookup"><span data-stu-id="6c631-258">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="6c631-259">Q # içindeki tüm diziler sıfır tabanlıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-259">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="6c631-260">Diğer bir deyişle, bir dizinin ilk öğesi `a` her zaman olur `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-260">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="6c631-261">Dizi dilimleri</span><span class="sxs-lookup"><span data-stu-id="6c631-261">Array Slices</span></span>

<span data-ttu-id="6c631-262">Bir dizi ifadesi ve bir `Range` ifade verildiğinde, `[` ve dizi dilimi işleci kullanılarak yeni bir ifade oluşturulabilir `]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-262">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="6c631-263">Yeni ifade, dizisiyle aynı türde olur ve tarafından tanımlanan sırada öğesi tarafından dizin oluşturulan dizi öğelerini içerir `Range` `Range` .</span><span class="sxs-lookup"><span data-stu-id="6c631-263">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="6c631-264">Örneğin, `a` bir dizi bir diziyle ilişkiliyse, ' ın `Double` `a[3..-1..0]` `Double[]` ilk dört öğesini, `a` ancak içinde göründükleri şekilde ters sırada içeren bir ifadedir `a` .</span><span class="sxs-lookup"><span data-stu-id="6c631-264">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="6c631-265">`Range`Boşsa, sonuçta elde edilen dizi dilimi sıfır uzunluğunda olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-265">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="6c631-266">Başvuran dizi öğelerinde olduğu gibi, dizi ifadesi basit bir tanımlayıcı değilse, dilimin dilimlemek için parantez içine alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="6c631-266">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="6c631-267">`a`Ve `b` dizilerinin her ikisi de varsa `Int` , birleştirme işleminden alınan bir dilim şöyle ifade edilir:</span><span class="sxs-lookup"><span data-stu-id="6c631-267">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="6c631-268">Çıkarılan başlangıç/bitiş değerleri</span><span class="sxs-lookup"><span data-stu-id="6c631-268">Inferred start/end values</span></span>

<span data-ttu-id="6c631-269">0,8 sürümümüzden başlayarak, Aralık Dilimleme için bağlamsal ifadeleri destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="6c631-269">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="6c631-270">Özellikle, Aralık başlangıç ve bitiş değerleri bir Aralık Dilimleme ifadesi bağlamında atlanabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-270">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="6c631-271">Bu durumda, derleyici aralığa yönelik istenen sınırlayıcıları çıkarması için aşağıdaki kuralları uygular.</span><span class="sxs-lookup"><span data-stu-id="6c631-271">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="6c631-272">Örneğin, Aralık başlangıç değeri atlanırsa, çıkarılan başlangıç değeri</span><span class="sxs-lookup"><span data-stu-id="6c631-272">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="6c631-273">bir adım belirtilmemişse veya belirtilen adım pozitifse sıfır ve</span><span class="sxs-lookup"><span data-stu-id="6c631-273">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6c631-274">, belirtilen adım negatifse, dilimli dizinin uzunluğu eksi bir değer.</span><span class="sxs-lookup"><span data-stu-id="6c631-274">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="6c631-275">Aralık bitiş değeri atlanırsa, çıkarılan bitiş değeri</span><span class="sxs-lookup"><span data-stu-id="6c631-275">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="6c631-276">, bir adım belirtilmediyse veya belirtilen adım pozitif ise ve</span><span class="sxs-lookup"><span data-stu-id="6c631-276">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="6c631-277">, belirtilen adım negatifse sıfırdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-277">is zero if the specified step is negative.</span></span> 

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

### <a name="copy-and-update-expressions"></a><span data-ttu-id="6c631-278">Kopyalama ve güncelleştirme Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-278">Copy-and-Update Expressions</span></span>

<span data-ttu-id="6c631-279">Tüm Q # türleri değer türleri olduğundan ve biraz özel bir rol alan qubits ile, bir değer bir simgeye bağlandığında veya bir sembol yeniden bağlandığında bir "kopya" oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="6c631-279">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="6c631-280">Yani, Q # davranışı atamadaki bir kopyanın oluşturulmasıyla aynı olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-280">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="6c631-281">Pratikte yalnızca ilgili parçalar gerektiği şekilde yeniden oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="6c631-281">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="6c631-282">Bu özellikle de diziler içerir.</span><span class="sxs-lookup"><span data-stu-id="6c631-282">This in particular also includes arrays.</span></span>
<span data-ttu-id="6c631-283">Özellikle, dizi öğelerini güncelleştirmek mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="6c631-283">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="6c631-284">Var olan bir diziyi değiştirmek için bir *kopyalama ve güncelleştirme* mekanizmasının kullanılmasını gerekir.</span><span class="sxs-lookup"><span data-stu-id="6c631-284">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="6c631-285">Yeni diziler, *kopyalama ve güncelleştirme* ifadeleri aracılığıyla mevcut olanlardan oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-285">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="6c631-286">Bir Copy-Update ifadesi formun bir ifadesidir `expression1 w/ expression2 <- expression3` , burada bir `expression1` tür için tür olması gerekir `T[]` `T` .</span><span class="sxs-lookup"><span data-stu-id="6c631-286">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="6c631-287">İkincisi, `expression2` içindeki diziye kıyasla değiştirilecek öğe dizinlerini tanımlar `expression1` ve türünden ya da `Int` türünde olmalıdır `Range` .</span><span class="sxs-lookup"><span data-stu-id="6c631-287">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="6c631-288">`expression2`Türünde ise `Int` , `expression3` türünde olması gerekir `T` .</span><span class="sxs-lookup"><span data-stu-id="6c631-288">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="6c631-289">`expression2`Türünde ise `Range` , `expression3` türünde olması gerekir `T[]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-289">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="6c631-290">Bir Copy-Update ifadesi, ' deki `arr w/ idx <- value` öğe (ler) i olarak ayarlanan öğeler hariç, içindeki öğesine karşılık gelen öğeye ayarlanmış olan yeni bir dizi oluşturur `arr` `idx` `value` .</span><span class="sxs-lookup"><span data-stu-id="6c631-290">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="6c631-291">Örneğin, `arr` bir dizi içeriyorsa `[0,1,2,3]` ,</span><span class="sxs-lookup"><span data-stu-id="6c631-291">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="6c631-292">`arr w/ 0 <- 10`dizi `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-292">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="6c631-293">`arr w/ 2 <- 10`dizi `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-293">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="6c631-294">`arr w/ 0..2..3 <- [10,12]`dizi `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-294">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="6c631-295">Adlandırılmış öğeler için kopyalama ve güncelleştirme ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-295">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="6c631-296">Kullanıcı tanımlı türlerde adlandırılmış öğeler için benzer ifadeler mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="6c631-296">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="6c631-297">Örneğin türü göz önünde bulundurun</span><span class="sxs-lookup"><span data-stu-id="6c631-297">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="6c631-298">`c`Türü değerini içeriyorsa `Complex(1., -1.)` ,, `c w/ Re <- 0.` olarak değerlendirilen türünde bir ifadedir `Complex` `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="6c631-298">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="6c631-299">Düzensiz Diziler</span><span class="sxs-lookup"><span data-stu-id="6c631-299">Jagged Arrays</span></span>

<span data-ttu-id="6c631-300">Bazen "dizi dizisi" olarak adlandırılan pürüzlü bir dizi, öğeleri dizi dizileri olan bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="6c631-300">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="6c631-301">Pürüzlü bir dizinin öğeleri farklı boyutlarda olabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-301">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="6c631-302">Aşağıdaki örnek, çarpma tablosunu temsil eden pürüzlü bir dizinin nasıl bildirilemeyeceğini ve başlatılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="6c631-302">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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

### <a name="arrays-of-callables"></a><span data-ttu-id="6c631-303">Callables dizileri</span><span class="sxs-lookup"><span data-stu-id="6c631-303">Arrays of callables</span></span> 

<span data-ttu-id="6c631-304">Çağrılabilir türlerle ilgili daha fazla ayrıntıyı aşağıda ve bir sonraki sayfada, [işlemler ve Q #](xref:microsoft.quantum.guide.operationsfunctions)' da işlevlerde bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6c631-304">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="6c631-305">Ortak öğe türü bir işlem ya da işlev türü ise, tüm öğeler aynı giriş ve çıkış türlerine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-305">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="6c631-306">Dizinin öğe türü tüm öğeleri tarafından desteklenen tüm nesneleri destekleyecektir.</span><span class="sxs-lookup"><span data-stu-id="6c631-306">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="6c631-307">Örneğin,, ve hepsi ise,, `Op1` `Op2` ve `Op3` `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` her ikisini de destekler, destekler ve `Op3` destekler:</span><span class="sxs-lookup"><span data-stu-id="6c631-307">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6c631-308">`[Op1, Op2]`, bir dizi `(Qubit[] => Unit)` işlemden oluşur.</span><span class="sxs-lookup"><span data-stu-id="6c631-308">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="6c631-309">`[Op1, Op3]`, bir dizi `(Qubit[] => Unit is Adj)` işlemden oluşur.</span><span class="sxs-lookup"><span data-stu-id="6c631-309">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="6c631-310">`[Op2, Op3]`, bir dizi `(Qubit[] => Unit is Ctl)` işlemden oluşur.</span><span class="sxs-lookup"><span data-stu-id="6c631-310">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="6c631-311">Ancak, `(Qubit[] => Unit is Adj)` ve `(Qubit[] => Unit is Ctl)` işlemleri ortak temel türüne sahip olsa `(Qubit[] => Unit)` da, bu işleçlerin dizilerinin ortak *of* bir temel türü paylaşmadığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="6c631-311">However, while `(Qubit[] => Unit is Adj)` and  `(Qubit[] => Unit is Ctl)` operations have the common base type of `(Qubit[] => Unit)`, note that arrays *of* these operators do not share a common base type.</span></span> <span data-ttu-id="6c631-312">Örneğin, `[[Op1], [Op2]]` Şu anda, uyumsuz dizi türlerinin bir dizisini oluşturmaya çalıştığı için bir hata oluşturur `(Qubit[] => Unit is Adj)[]` `(Qubit[] => Unit is Ctl)[]` .</span><span class="sxs-lookup"><span data-stu-id="6c631-312">For example, `[[Op1], [Op2]]` would currently raise an error because it is attempting to create an array of the incompatible array types `(Qubit[] => Unit is Adj)[]` and `(Qubit[] => Unit is Ctl)[]`.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="6c631-313">Koşullu Ifadeler</span><span class="sxs-lookup"><span data-stu-id="6c631-313">Conditional Expressions</span></span>

<span data-ttu-id="6c631-314">Aynı türde ve bir Boolean ifadesinin iki diğer ifadesi verildiğinde, koşullu ifade soru işareti `?` ve dikey çubuk kullanılarak oluşturulmuş olabilir `|` .</span><span class="sxs-lookup"><span data-stu-id="6c631-314">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="6c631-315">Örneğin, `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="6c631-315">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="6c631-316">Bu örnekte, koşullu ifadenin değeri `c` `a==b` true, ise false ise olur `d` .</span><span class="sxs-lookup"><span data-stu-id="6c631-316">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="6c631-317">Callables ile koşullu ifadeler</span><span class="sxs-lookup"><span data-stu-id="6c631-317">Conditional expressions with callables</span></span>

<span data-ttu-id="6c631-318">İki ifade, aynı girişlere ve çıkışlara sahip olan ancak farklı komik desteği olan işlemlere göre değerlendirilemez.</span><span class="sxs-lookup"><span data-stu-id="6c631-318">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="6c631-319">Bu durumda, koşullu ifadenin türü, her iki ifade tarafından desteklenen tüm semantikleri destekleyen bu giriş ve çıkışlarla bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-319">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="6c631-320">Örneğin,, ve hepsi ise,, `Op1` `Op2` ve `Op3` `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` her ikisini de destekler, destekler ve `Op3` destekler:</span><span class="sxs-lookup"><span data-stu-id="6c631-320">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="6c631-321">`flag ? Op1 | Op2`bir `(Qubit[] => Unit)` işlemdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-321">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="6c631-322">`flag ? Op1 | Op3`bir `(Qubit[] => Unit is Adj)` işlemdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-322">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="6c631-323">`flag ? Op2 | Op3`bir `(Qubit[] => Unit is Ctl)` işlemdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-323">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="6c631-324">Olası iki sonuç ifadesi varsa, bir işlev veya işlem çağrısı içeriyorsa, bu çağrı yalnızca çağrının değeri olacak şekilde gerçekleşdiğinde olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-324">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="6c631-325">Örneğin, bu durumda, `a==b ? C(qs) | D(qs)` `a==b` true ise `C` işlem çağrılacaktır ve false ise yalnızca `D` çağrılacaktır.</span><span class="sxs-lookup"><span data-stu-id="6c631-325">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="6c631-326">Bu, diğer dillerdeki kısa devre 'ya benzer.</span><span class="sxs-lookup"><span data-stu-id="6c631-326">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="6c631-327">Çağrılabilir Ifadeler</span><span class="sxs-lookup"><span data-stu-id="6c631-327">Callable Expressions</span></span>

<span data-ttu-id="6c631-328">Çağrılabilir sabit değer, derleme kapsamında tanımlanan bir işlemin veya işlevin adıdır.</span><span class="sxs-lookup"><span data-stu-id="6c631-328">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="6c631-329">Örneğin, `X` standart kitaplık işlemine başvuran bir işlem sabit değeri `X` ve `Message` standart kitaplık işlevine başvuran bir işlev sabit değeri `Message` .</span><span class="sxs-lookup"><span data-stu-id="6c631-329">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="6c631-330">Bir işlem `Adjoint` functor destekliyorsa, `Adjoint op` bir işlem ifadesi olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-330">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="6c631-331">Benzer şekilde, işlem `Controlled` functor 'ı destekliyorsa, `Controlled op` bir işlem ifadesi olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-331">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="6c631-332">Bu ifadelerin türleri [çağıran işlem özelleştirmeleri](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)sırasında belirtilmiştir.</span><span class="sxs-lookup"><span data-stu-id="6c631-332">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="6c631-333">Funörler ( `Adjoint` ve `Controlled` ), Unwrap operatörü `!` ve [] ' ile dizi dizini oluşturma dışında diğer işleçlerden daha yakından bağlanır.</span><span class="sxs-lookup"><span data-stu-id="6c631-333">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="6c631-334">Bu nedenle, işlemlerin kullanılan funları destekledikleri varsayılarak şunlar geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="6c631-334">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="6c631-335">Tür parametreli çağrılabilir ifadeler</span><span class="sxs-lookup"><span data-stu-id="6c631-335">Type-parameterized callable expressions</span></span>

<span data-ttu-id="6c631-336">Çağrılabilir bir sabit değer olarak kullanılabilir, bir değişkene atamak veya başka bir çağrılabilir öğesine geçirmek için deyin.</span><span class="sxs-lookup"><span data-stu-id="6c631-336">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="6c631-337">Bu durumda, çağrılabilir [tür parametrelerine](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)sahipse, çağrılabilir değerin bir parçası olarak sağlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="6c631-337">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="6c631-338">Çağrılabilir bir değer belirtilmeyen tür parametrelerine sahip olamaz.</span><span class="sxs-lookup"><span data-stu-id="6c631-338">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="6c631-339">Örneğin, `Fun` imzasına sahip bir işlevdir `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="6c631-339">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="6c631-340">Çağrılabilir çağırma Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="6c631-340">Callable Invocation Expressions</span></span>

<span data-ttu-id="6c631-341">Çağrılabilir bir (işlem veya işlev) ifadesi ve çağrılabilir öğesinin giriş türünün bir tanımlama grubu ifadesi verildiğinde, çağrılabilir ifadeye kayıt kümesi ifadesi eklenerek bir çağırma ifadesi oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-341">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="6c631-342">Çağırma ifadesinin türü, çağrılabilir olan imzanın çıkış türüdür.</span><span class="sxs-lookup"><span data-stu-id="6c631-342">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="6c631-343">Örneğin, `Op` imzaya sahip bir işlem ise `((Int, Qubit) => Double)` , `Op(3, qubit1)` türünde bir ifadedir `Double` .</span><span class="sxs-lookup"><span data-stu-id="6c631-343">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6c631-344">Benzer şekilde, `Sin` imzaya sahip bir `(Double -> Double)` `Sin(0.1)` işlevsiyse, türünde bir ifadedir `Double` .</span><span class="sxs-lookup"><span data-stu-id="6c631-344">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="6c631-345">Son olarak, `Builder` imza içeren bir işlevdir `(Int -> (Int -> Int))` ,, `Builder(3)` öğesinden Int 'e kadar bir işlevdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-345">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="6c631-346">Çağrılabilir değerli bir ifadenin sonucunu çağırmak, çağrılabilir ifade etrafında fazladan bir çift parantez gerektirir.</span><span class="sxs-lookup"><span data-stu-id="6c631-346">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="6c631-347">Bu nedenle, önceki paragraftan çağırma sonucunu çağırmak için `Builder` doğru sözdizimi şöyledir:</span><span class="sxs-lookup"><span data-stu-id="6c631-347">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="6c631-348">Bir [tür parametreli](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) çağrılabilir çağırılırken, gerçek tür parametreleri açılı ayraç içinde `<` ve `>` çağrılabilir ifadeden sonra belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="6c631-348">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="6c631-349">Q # derleyicisi gerçek türleri çıkardığı için bu genellikle gereksizdir.</span><span class="sxs-lookup"><span data-stu-id="6c631-349">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="6c631-350">Ancak, tür parametreli bir bağımsız değişken belirtilmemişse, [kısmi uygulama](xref:microsoft.quantum.guide.operationsfunctions#partial-application) *için gereklidir.*</span><span class="sxs-lookup"><span data-stu-id="6c631-350">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="6c631-351">Ayrıca bazen farklı functor ile işlemleri bir çağrılabilir olarak geçirirken yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="6c631-351">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="6c631-352">Örneğin, imzası varsa `Func` ve imza `('T1, 'T2, 'T1) -> 'T2` içeriyorsa `Op1` `Op2` `(Qubit[] => Unit is Adj)` ve `Op3` `(Qubit[] => Unit)` `Func` `Op1` ilk bağımsız değişken olarak, `Op2` ikinci olarak ve üçüncü olarak çağırmak için imza varsa `Op3` :</span><span class="sxs-lookup"><span data-stu-id="6c631-352">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="6c631-353">Tür belirtimi gereklidir çünkü `Op3` ve `Op1` farklı türlere sahip olur, bu nedenle derleyici bunu belirtim olmadan belirsiz olarak değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="6c631-353">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="6c631-354">İşleç Önceliği</span><span class="sxs-lookup"><span data-stu-id="6c631-354">Operator Precedence</span></span>

<span data-ttu-id="6c631-355">Tüm ikili işleçler, hariç olmak üzere, doğru ilişkilendirilebilir `^` .</span><span class="sxs-lookup"><span data-stu-id="6c631-355">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="6c631-356">Parantez ve `[` `]` dizi Dilimleme ve dizin oluşturma için herhangi bir işleçten önce bağlayın.</span><span class="sxs-lookup"><span data-stu-id="6c631-356">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="6c631-357">`Adjoint`Ve `Controlled` diğer tüm işleçlerden önce, dizi dizinlemesi ve sonra bağlama.</span><span class="sxs-lookup"><span data-stu-id="6c631-357">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="6c631-358">İşlem ve işlev çağırma parantezleri aynı zamanda herhangi bir işleçten önce, ancak dizi dizinlemesi ve komik bir şekilde bağlanır.</span><span class="sxs-lookup"><span data-stu-id="6c631-358">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="6c631-359">En yüksekten en düşüğe göre öncelik sırasına göre işleçler:</span><span class="sxs-lookup"><span data-stu-id="6c631-359">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="6c631-360">Operatör</span><span class="sxs-lookup"><span data-stu-id="6c631-360">Operator</span></span> | <span data-ttu-id="6c631-361">Sayısına</span><span class="sxs-lookup"><span data-stu-id="6c631-361">Arity</span></span> | <span data-ttu-id="6c631-362">Description</span><span class="sxs-lookup"><span data-stu-id="6c631-362">Description</span></span> | <span data-ttu-id="6c631-363">İşlenen türleri</span><span class="sxs-lookup"><span data-stu-id="6c631-363">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="6c631-364">arkasında`!`</span><span class="sxs-lookup"><span data-stu-id="6c631-364">trailing `!`</span></span> | <span data-ttu-id="6c631-365">Birli</span><span class="sxs-lookup"><span data-stu-id="6c631-365">Unary</span></span> | <span data-ttu-id="6c631-366">Unwrap</span><span class="sxs-lookup"><span data-stu-id="6c631-366">Unwrap</span></span> | <span data-ttu-id="6c631-367">Kullanıcı tanımlı herhangi bir tür</span><span class="sxs-lookup"><span data-stu-id="6c631-367">Any user-defined type</span></span>
 <span data-ttu-id="6c631-368">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="6c631-368">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="6c631-369">Birli</span><span class="sxs-lookup"><span data-stu-id="6c631-369">Unary</span></span> | <span data-ttu-id="6c631-370">Sayısal negatif, bit düzeyinde tamamlama, mantıksal değilleme</span><span class="sxs-lookup"><span data-stu-id="6c631-370">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="6c631-371">`Int`, için `BigInt` veya için `Double` `-` `Int` veya `BigInt` `~~~` `Bool` için`not`</span><span class="sxs-lookup"><span data-stu-id="6c631-371">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="6c631-372">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-372">Binary</span></span> | <span data-ttu-id="6c631-373">Tamsayı güç</span><span class="sxs-lookup"><span data-stu-id="6c631-373">Integer power</span></span> | <span data-ttu-id="6c631-374">`Int`üs için veya `BigInt` taban için `Int`</span><span class="sxs-lookup"><span data-stu-id="6c631-374">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="6c631-375">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="6c631-375">`/`, `*`, `%`</span></span> | <span data-ttu-id="6c631-376">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-376">Binary</span></span> | <span data-ttu-id="6c631-377">Bölme, çarpma, tamsayı mod</span><span class="sxs-lookup"><span data-stu-id="6c631-377">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="6c631-378">`Int`, `BigInt` veya `Double` için `/` `*` `Int` veya `BigInt` için`%`</span><span class="sxs-lookup"><span data-stu-id="6c631-378">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="6c631-379">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="6c631-379">`+`, `-`</span></span> | <span data-ttu-id="6c631-380">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-380">Binary</span></span> | <span data-ttu-id="6c631-381">Ekleme veya dize ve dizi birleştirme, çıkarma</span><span class="sxs-lookup"><span data-stu-id="6c631-381">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="6c631-382">`Int``BigInt`veya `Double` `String` için bir dizi türü veya`+`</span><span class="sxs-lookup"><span data-stu-id="6c631-382">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="6c631-383">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="6c631-383">`<<<`, `>>>`</span></span> | <span data-ttu-id="6c631-384">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-384">Binary</span></span> | <span data-ttu-id="6c631-385">Sol SHIFT, sağa kaydırma</span><span class="sxs-lookup"><span data-stu-id="6c631-385">Left shift, right shift</span></span> | <span data-ttu-id="6c631-386">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6c631-386">`Int` or `BigInt`</span></span>
 <span data-ttu-id="6c631-387">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="6c631-387">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="6c631-388">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-388">Binary</span></span> | <span data-ttu-id="6c631-389">Küçüktür, küçüktür veya eşittir, büyüktür, büyüktür veya eşittir karşılaştırmaları</span><span class="sxs-lookup"><span data-stu-id="6c631-389">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="6c631-390">`Int``BigInt`veya`Double`</span><span class="sxs-lookup"><span data-stu-id="6c631-390">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="6c631-391">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="6c631-391">`==`, `!=`</span></span> | <span data-ttu-id="6c631-392">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-392">Binary</span></span> | <span data-ttu-id="6c631-393">eşit, eşit olmayan karşılaştırmalar</span><span class="sxs-lookup"><span data-stu-id="6c631-393">equal, not-equal comparisons</span></span> | <span data-ttu-id="6c631-394">herhangi bir ilkel tür</span><span class="sxs-lookup"><span data-stu-id="6c631-394">any primitive type</span></span>
 `&&&` | <span data-ttu-id="6c631-395">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-395">Binary</span></span> | <span data-ttu-id="6c631-396">Bit düzeyinde AND</span><span class="sxs-lookup"><span data-stu-id="6c631-396">Bitwise AND</span></span> | <span data-ttu-id="6c631-397">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6c631-397">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="6c631-398">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-398">Binary</span></span> | <span data-ttu-id="6c631-399">Bit düzeyinde XOR</span><span class="sxs-lookup"><span data-stu-id="6c631-399">Bitwise XOR</span></span> | <span data-ttu-id="6c631-400">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6c631-400">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="6c631-401">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-401">Binary</span></span> | <span data-ttu-id="6c631-402">Bit düzeyinde OR</span><span class="sxs-lookup"><span data-stu-id="6c631-402">Bitwise OR</span></span> | <span data-ttu-id="6c631-403">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="6c631-403">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="6c631-404">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-404">Binary</span></span> | <span data-ttu-id="6c631-405">Mantıksal VE</span><span class="sxs-lookup"><span data-stu-id="6c631-405">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="6c631-406">İkili</span><span class="sxs-lookup"><span data-stu-id="6c631-406">Binary</span></span> | <span data-ttu-id="6c631-407">Mantıksal EĞER</span><span class="sxs-lookup"><span data-stu-id="6c631-407">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="6c631-408">İkili/üçlü</span><span class="sxs-lookup"><span data-stu-id="6c631-408">Binary/Ternary</span></span> | <span data-ttu-id="6c631-409">Range işleci</span><span class="sxs-lookup"><span data-stu-id="6c631-409">Range operator</span></span> | `Int`
 <span data-ttu-id="6c631-410">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="6c631-410">`?` `|`</span></span> | <span data-ttu-id="6c631-411">Üçlü</span><span class="sxs-lookup"><span data-stu-id="6c631-411">Ternary</span></span> | <span data-ttu-id="6c631-412">Koşullu</span><span class="sxs-lookup"><span data-stu-id="6c631-412">Conditional</span></span> | <span data-ttu-id="6c631-413">`Bool`Sol taraftaki</span><span class="sxs-lookup"><span data-stu-id="6c631-413">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="6c631-414">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="6c631-414">`w/` `<-`</span></span> | <span data-ttu-id="6c631-415">Üçlü</span><span class="sxs-lookup"><span data-stu-id="6c631-415">Ternary</span></span> | <span data-ttu-id="6c631-416">Kopyala ve Güncelleştir</span><span class="sxs-lookup"><span data-stu-id="6c631-416">Copy-and-update</span></span> | <span data-ttu-id="6c631-417">bkz. [kopyalama ve güncelleştirme ifadeleri](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="6c631-417">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c631-418">Sonraki adımlar</span><span class="sxs-lookup"><span data-stu-id="6c631-418">Next steps</span></span>

<span data-ttu-id="6c631-419">Artık Q # ' da ifadelerle çalışdığınıza göre, işlem ve işlevlerin nasıl tanımlanacağını ve çağrılacağını öğrenmek için [q # Içindeki işlemlere ve işlevlere](xref:microsoft.quantum.guide.operationsfunctions) gidebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6c631-419">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>
