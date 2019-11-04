---
title: İfadeler | Microsoft Docs
description: İfadeler
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 09d493df4e1178fee1f7a5946cfda2f411111006
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185214"
---
# <a name="expressions"></a><span data-ttu-id="9fc6c-103">İfadeler</span><span class="sxs-lookup"><span data-stu-id="9fc6c-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="9fc6c-104">Gruplama</span><span class="sxs-lookup"><span data-stu-id="9fc6c-104">Grouping</span></span>

<span data-ttu-id="9fc6c-105">Herhangi bir ifade verildiğinde, parantez içine alınmış aynı ifade aynı türde bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="9fc6c-106">Örneğin, `(7)` `Int` bir ifadedir, `([1,2,3])` `Int`s dizisi türünde bir ifadedir ve `((1,2))` türü `(Int, Int)`olan bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="9fc6c-107">[Tür modelinde](xref:microsoft.quantum.language.type-model#tuple-types) açıklanan basit değerler ve tek öğeli tanımlama grupları arasındaki denklik, grup olarak `(6)` ve tek öğeli tanımlama grubu olarak `(6)` arasındaki belirsizlik ortadan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="9fc6c-108">Symbols</span><span class="sxs-lookup"><span data-stu-id="9fc6c-108">Symbols</span></span>

<span data-ttu-id="9fc6c-109">`'T` türünde bir değere atanan veya atanan bir simgenin adı `'T`türünde bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="9fc6c-110">Örneğin, sembol `count` `5`tamsayı değerine bağlıysa `count` bir tamsayı ifadesi olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="9fc6c-111">Sayısal Ifadeler</span><span class="sxs-lookup"><span data-stu-id="9fc6c-111">Numeric Expressions</span></span>

<span data-ttu-id="9fc6c-112">Sayısal ifadeler `Int`, `BigInt`veya `Double`türündeki ifadelerdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="9fc6c-113">Diğer bir deyişle, tamsayı veya kayan noktalı sayılardır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="9fc6c-114">`Int` değişmez değerleri, sonunda "l" veya "L C#" gerekli olmadığında (veya izin verilmeyen), içindeki tamsayı değişmez değerleri ile aynıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="9fc6c-115">Onaltılık ve ikili tamsayılar sırasıyla bir "0x" ve "0b" önekiyle desteklenir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="9fc6c-116">`BigInt` değişmez değerleri, "l" veya "L" ile birlikte .NET 'teki büyük tamsayı dizeleriyle aynıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="9fc6c-117">Onaltılık büyük tamsayılar bir "0x" öneki ile desteklenir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="9fc6c-118">Bu nedenle, `BigInt` değişmez değerlerin geçerli kullanımları aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="9fc6c-119">`Double` değişmez değerler, sonunda "d" veya "D C#" gerekli olmadığında (veya izin verilmeyen), içindeki çift değişmez değerler ile aynıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="9fc6c-120">Herhangi bir öğe türünün dizi ifadesi verildiğinde, bir `Int` ifadesi, parantez, `(` ve `)`içine alınmış dizi ifadesi ile `Length` yerleşik işlevi kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="9fc6c-121">Örneğin, `a` bir diziye bağlıysa `Length(a)` bir tamsayı ifadesidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="9fc6c-122">`b` tamsayılar dizi diziyse `Int[][]`, `Length(b)` `b`içindeki alt dizilerin sayısıdır ve `Length(b[1])` `b`ikinci alt dizideki tamsayıların sayısıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="9fc6c-123">Aynı türde iki sayısal ifade verildiğinde, ikili işleçler `+`, `-`, `*`ve `/` yeni bir sayısal ifade oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="9fc6c-124">Yeni ifadenin türü, bileşen ifadelerinin türleriyle aynı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="9fc6c-125">İki tamsayı ifadesi verildiğinde, ikili işleç `^` (güç) yeni bir tamsayı ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="9fc6c-126">Benzer şekilde, `^` yeni bir Double ifadesi oluşturmak için iki Double ifadesiyle birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="9fc6c-127">Son olarak, `^` solda büyük bir tam sayı ile, yeni bir büyük tamsayı ifadesi oluşturmak için sağdaki bir tamsayı ile kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="9fc6c-128">Bu durumda, ikinci parametrenin 32 bite sığması gerekir; Aksi takdirde, bir çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="9fc6c-129">İki tamsayı veya büyük tamsayı ifadesi verildiğinde, yeni bir tamsayı veya büyük tamsayı ifadesi `%` (mod), `&&&` (bit düzeyinde ve), `|||` (bit düzeyinde OR) veya `^^^` (bit düzeyinde XOR) işleçleri kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="9fc6c-130">Sol tarafta bir tamsayı veya büyük tamsayı ifadesi ve sağ tarafta bir tamsayı ifadesi verildiğinde, sol taraftaki ile aynı türde yeni bir ifade oluşturmak için `<<<` (aritmetik sol SHIFT) veya `>>>` (aritmetik sağa kaydırma) işleçleri kullanılabilir ifadesini.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="9fc6c-131">Kaydırma işleminin ikinci parametresi (SHIFT miktarı) sıfırdan büyük veya sıfıra eşit olmalıdır; negatif kaydırma miktarları için davranış tanımsızdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="9fc6c-132">Her iki vardiya işlemi için de SHIFT miktarı 32 bite uyum sağlamalıdır; Aksi takdirde, bir çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="9fc6c-133">Kaydırılan sayı bir tamsayı ise, kaydırma miktarı yorumlanır `mod 64`; Yani, 1 ' in bir vardiyası ve 65 vardiyası aynı etkiye sahiptir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="9fc6c-134">Hem tamsayı hem de büyük tamsayı değerleri için, vardiyalar aritmetik değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="9fc6c-135">Negatif bir değeri sol veya sağ kaydırma, negatif bir sayı ile sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="9fc6c-136">Diğer bir deyişle, bir adım sola veya sağa kaydırma, sırasıyla 2 ile çarpılarak veya bölünerek tamamen aynıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="9fc6c-137">Tamsayı bölme ve tamsayı mod, negatif sayılar için aynı davranışı izler C#.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="9fc6c-138">Diğer bir deyişle `a % b` her zaman `a`aynı işarete sahip olur ve `b * (a / b) + a % b` her zaman `a`eşit olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="9fc6c-139">Örnek:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="9fc6c-140">5</span><span class="sxs-lookup"><span data-stu-id="9fc6c-140">5</span></span> | <span data-ttu-id="9fc6c-141">2</span><span class="sxs-lookup"><span data-stu-id="9fc6c-141">2</span></span> | <span data-ttu-id="9fc6c-142">2</span><span class="sxs-lookup"><span data-stu-id="9fc6c-142">2</span></span> | <span data-ttu-id="9fc6c-143">1</span><span class="sxs-lookup"><span data-stu-id="9fc6c-143">1</span></span>
 <span data-ttu-id="9fc6c-144">5</span><span class="sxs-lookup"><span data-stu-id="9fc6c-144">5</span></span> | <span data-ttu-id="9fc6c-145">-2</span><span class="sxs-lookup"><span data-stu-id="9fc6c-145">-2</span></span> | <span data-ttu-id="9fc6c-146">-2</span><span class="sxs-lookup"><span data-stu-id="9fc6c-146">-2</span></span> | <span data-ttu-id="9fc6c-147">1</span><span class="sxs-lookup"><span data-stu-id="9fc6c-147">1</span></span>
 <span data-ttu-id="9fc6c-148">-5</span><span class="sxs-lookup"><span data-stu-id="9fc6c-148">-5</span></span> | <span data-ttu-id="9fc6c-149">2</span><span class="sxs-lookup"><span data-stu-id="9fc6c-149">2</span></span> | <span data-ttu-id="9fc6c-150">-2</span><span class="sxs-lookup"><span data-stu-id="9fc6c-150">-2</span></span> | <span data-ttu-id="9fc6c-151">-1</span><span class="sxs-lookup"><span data-stu-id="9fc6c-151">-1</span></span>
 <span data-ttu-id="9fc6c-152">-5</span><span class="sxs-lookup"><span data-stu-id="9fc6c-152">-5</span></span> | <span data-ttu-id="9fc6c-153">-2</span><span class="sxs-lookup"><span data-stu-id="9fc6c-153">-2</span></span> | <span data-ttu-id="9fc6c-154">2</span><span class="sxs-lookup"><span data-stu-id="9fc6c-154">2</span></span> | <span data-ttu-id="9fc6c-155">-1</span><span class="sxs-lookup"><span data-stu-id="9fc6c-155">-1</span></span>

<span data-ttu-id="9fc6c-156">Büyük tamsayı bölme ve mod aynı şekilde çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="9fc6c-157">Herhangi bir sayısal ifade verildiğinde, yeni bir ifade `-` birli işleç kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="9fc6c-158">Yeni ifade, anayent ifadesiyle aynı türde olacaktır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="9fc6c-159">Herhangi bir tamsayı veya büyük tamsayı ifadesi verildiğinde, aynı türde yeni bir ifade `~~~` (bit düzeyinde tamamlayıcı) birli işleç kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="9fc6c-160">Boole Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-160">Boolean Expressions</span></span>

<span data-ttu-id="9fc6c-161">İki `Bool` değişmez değer `true` ve `false`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="9fc6c-162">Aynı ilkel türün herhangi iki ifadesi verildiğinde, `==` ve `!=` ikili işleçleri `Bool` ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="9fc6c-163">İki ifade (yanıt olarak) eşitse ifade true olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-163">The expression will be true if the two expressions are (resp. are not) equal.</span></span>

<span data-ttu-id="9fc6c-164">Kullanıcı tanımlı türlerin değerleri karşılaştırılamayabilir, yalnızca değerleri karşılaştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-164">Values of user-defined types may not be compared, only their values can be compared.</span></span> <span data-ttu-id="9fc6c-165">Örneğin,</span><span class="sxs-lookup"><span data-stu-id="9fc6c-165">For example,</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="9fc6c-166">`Qubit` değerleri için eşitlik karşılaştırması, kimlik eşitliğini; diğer bir deyişle, iki ifadenin aynı qubit 'i tanımlamasına bakılmaksızın.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="9fc6c-167">İki qubits 'in durumu karşılaştırılmaz, erişilmez, ölçülemez veya bu karşılaştırma tarafından değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="9fc6c-168">`Double` değerleri için eşitlik karşılaştırması, yuvarlama etkileri nedeniyle yanıltıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="9fc6c-169">Örneğin, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="9fc6c-170">İki sayısal ifade verildiğinde, `>`, `<`, `>=`ve `<=` ikili işleçleri, ilk ifade sırasıyla şundan büyükse, küçüktür, büyüktür veya eşittir olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir ya da ikinci ifadeye eşit veya daha az.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="9fc6c-171">İki Boolean ifade verildiğinde `and` ve `or` ikili işleçleri, iki ifadenin her ikisi de (her ikisi de veya her ikisi de) doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="9fc6c-172">Herhangi bir Boole ifadesi verildiğinde, anayent ifadesi false olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için `not` birli işleç kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="9fc6c-173">Dize Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-173">String Expressions</span></span>

<span data-ttu-id="9fc6c-174">Q # `fail` ifadesinde ve `Log` standart işlevinde dizelerin kullanılmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="9fc6c-175">Q # içindeki dizeler, değişmez değer veya enterpolasyonlu dizelerdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="9fc6c-176">Dize sabit değerleri çoğu dilde basit dize sabit değerlerine benzer: çift tırnak içine alınmış bir Unicode karakter dizisi, `"`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="9fc6c-177">Bir dizenin içinde, ters eğik çizgi karakteri `\` bir çift tırnak karakteriyle çıkmak ve yeni satır `\n`, bir satır geri dönüş `\r`ve `\t`olarak bir sekme eklemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="9fc6c-178">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="9fc6c-179">Dize enterpolasyonları için Q # sözdizimi, C# 7,0 sözdiziminin bir alt kümesidir; S #, tam (çok satırlı) enterpolasyonlu dizeleri desteklemez.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="9fc6c-180">C# Sözdizimi için bkz. [*enterpolasyonlu dizeler*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) .</span><span class="sxs-lookup"><span data-stu-id="9fc6c-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="9fc6c-181">Enterpolasyonlu bir dizenin içindeki ifadeler, sözdizimi değil C# , Q # söz dizimini izler.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="9fc6c-182">Geçerli bir Q # ifadesi, enterpolasyonlu bir dizede görünebilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="9fc6c-183">Qubit Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-183">Qubit Expressions</span></span>

<span data-ttu-id="9fc6c-184">Tek `Qubit` ifadeleri, `Qubit` dizilerinin `Qubit` değerlerine veya dizi öğelerine bağlanan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="9fc6c-185">`Qubit` değişmez değer yok.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="9fc6c-186">Pauli Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-186">Pauli Expressions</span></span>

<span data-ttu-id="9fc6c-187">Dört `Pauli` değeri, `PauliI`, `PauliX`, `PauliY`ve `PauliZ`tüm geçerli `Pauli` ifadeleridir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="9fc6c-188">Bunun dışında, tek `Pauli` ifadeleri, `Pauli` dizilerinin `Pauli` değerlerine veya dizi öğelerine bağlanan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="9fc6c-189">Sonuç Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-189">Result Expressions</span></span>

<span data-ttu-id="9fc6c-190">İki `Result` değeri `One` ve `Zero`geçerli `Result` ifadeleridir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="9fc6c-191">Bunun dışında, tek `Result` ifadeleri, `Result` dizilerinin `Result` değerlerine veya dizi öğelerine bağlanan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="9fc6c-192">Özellikle, `One` tamsayı `1`ile aynı değildir ve aralarında doğrudan dönüşüm yoktur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="9fc6c-193">`Zero` ve `0`için de aynı değer geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="9fc6c-194">Aralık Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-194">Range Expressions</span></span>

<span data-ttu-id="9fc6c-195">`start`, `step`ve `stop`olmak üzere üç `Int` ifade verildiğinde `start .. step .. stop`, ilk öğesi `start`, ikinci öğe ise `start+step`, üçüncü öğe ise `start+step+step`geçirilene kadar bir Aralık deyimidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="9fc6c-196">Örneğin, `step` pozitif ve `stop < start`olduğunda bir Aralık boş olabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="9fc6c-197">Aralığın son öğesi, `start` ve `stop` arasındaki fark `step`bir tam sayı `stop` olur. diğer bir deyişle, Aralık her iki uçta da dahil olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="9fc6c-198">`start` ve `stop`iki `Int` ifadesi verildiğinde `start .. stop`, `start .. 1 .. stop`eşit bir Aralık ifadesidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="9fc6c-199">`stop` `start`'den az olsa bile, kapsanan `step` + 1 olduğunu unutmayın. Böyle bir durumda, Aralık boştur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="9fc6c-200">Bazı örnek aralıklar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-200">Some example ranges are:</span></span>

- <span data-ttu-id="9fc6c-201">`1..3` 1, 2, 3 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="9fc6c-202">`2..2..5` 2, 4 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="9fc6c-203">`2..2..6`, 2, 4, 6 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="9fc6c-204">`6..-2..2` 6, 4, 2 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="9fc6c-205">boş Aralık `2..1`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="9fc6c-206">`2..6..7` aralığı 2 ' dir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="9fc6c-207">boş Aralık `2..2..1`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="9fc6c-208">boş Aralık `1..-1..2`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="9fc6c-209">Çağrılabilir Ifadeler</span><span class="sxs-lookup"><span data-stu-id="9fc6c-209">Callable Expressions</span></span>

<span data-ttu-id="9fc6c-210">Çağrılabilir sabit değer, derleme kapsamında tanımlanan bir işlemin veya işlevin adıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="9fc6c-211">Örneğin, `X` standart kitaplık `X` işlemine başvuran bir işlem değişmez değeri ve `Message` standart kitaplık `Message` işlevine başvuran bir işlev sabit değeri.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="9fc6c-212">Bir işlem `Adjoint` functor destekliyorsa, `Adjoint op` bir işlem ifadesi olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="9fc6c-213">Benzer şekilde, işlem `Controlled` functor destekliyorsa, `Controlled op` bir işlem ifadesi olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="9fc6c-214">Bu ifadelerin türleri, [Funörler](xref:microsoft.quantum.language.type-model#functors)içinde belirtilmiştir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="9fc6c-215">Funörler (`Adjoint` ve `Controlled`), sarmalama işleci olmayan `!` ve `[]`ile dizi dizini oluşturma dışında diğer işleçlerden daha yakından bağlanır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="9fc6c-216">Bu nedenle, işlemlerin kullanılan funları destekledikleri varsayılarak şunlar geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="9fc6c-217">Çağrılabilir bir sabit değer olarak kullanılabilir, bir değişkene atamak veya başka bir çağrılabilir öğesine geçirmek için deyin.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="9fc6c-218">Bu durumda, çağrılabilir tür parametrelerine sahipse, çağrılabilir değerin bir parçası olarak sağlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="9fc6c-219">Çağrılabilir bir değer belirtilmeyen tür parametrelerine sahip olamaz.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="9fc6c-220">Örneğin, `Fun` imza içeren bir işlevdir `'T1->Unit`:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="9fc6c-221">Çağrılabilir çağırma Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="9fc6c-222">Çağrılabilir bir (işlem veya işlev) ifadesi ve çağrılabilir öğesinin giriş türünün bir tanımlama grubu ifadesi verildiğinde, çağrılabilir ifadeye kayıt kümesi ifadesi eklenerek bir çağırma ifadesi oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="9fc6c-223">Çağırma ifadesinin türü, çağrılabilir olan imzanın çıkış türüdür.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="9fc6c-224">Örneğin, `Op` imza `((Int, Qubit) => Double)`olan bir işlem ise, `Op(3, qubit1)` `Double`türünde bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="9fc6c-225">Benzer şekilde, `Sin` imza `(Double -> Double)`olan bir işlevdir, `Sin(0.1)` `Double`türünde bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="9fc6c-226">Son olarak, `Builder` imza `(Int -> (Int -> Int))`olan bir işlevdir, `Builder(3)` bir fonksiyondan Int 'e kadar olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="9fc6c-227">Çağrılabilir değerli bir ifadenin sonucunu çağırmak, çağrılabilir ifade etrafında fazladan bir çift parantez gerektirir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="9fc6c-228">Bu nedenle, önceki paragraftan `Builder` çağırma sonucunu çağırmak için doğru sözdizimi şöyledir:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="9fc6c-229">Bir tür parametreli çağrılabilir çağrılırken, gerçek tür parametreleri açılı `<` ayraç içinde ve çağrılabilir ifadeden sonra `>` belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="9fc6c-230">Q # derleyicisi gerçek türleri çıkardığı için bu genellikle gereksizdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="9fc6c-231">Bir tür parametreli bağımsız değişken belirtilmemişse, kısmi uygulama (aşağıya bakın) için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="9fc6c-232">Ayrıca bazen farklı functor ile işlemleri bir çağrılabilir olarak geçirirken yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="9fc6c-233">Örneğin, `Func` imza `('T1, 'T2, 'T1) -> 'T2`, `Op1` ve `Op2` imza `(Qubit[] => Unit is Adj)`varsa ve `Op3` ilk bağımsız değişken olarak `(Qubit[] => Unit)`çağırmak için `Func` imza `Op1`, ikinci olarak `Op2` ve üçüncü olarak `Op3`:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="9fc6c-234">Tür belirtimi gereklidir çünkü `Op3` ve `Op1` farklı türlere sahip olduğundan, derleyici bunu belirtim olmadan belirsiz olarak değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="9fc6c-235">Kısmi uygulama</span><span class="sxs-lookup"><span data-stu-id="9fc6c-235">Partial Application</span></span>

<span data-ttu-id="9fc6c-236">Çağrılabilir bir ifade verildiğinde, çağrılabilir bir bağımsız değişkenlerin alt kümesini sağlayarak yeni bir çağrılabilir oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="9fc6c-237">Buna _kısmi uygulama_denir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-237">This is called _partial application_.</span></span>

<span data-ttu-id="9fc6c-238">Q # ' da, kısmen uygulanan çağrılabilir bir normal çağırma ifadesi yazılarak, ancak belirtilmemiş bağımsız değişkenler için `_`alt çizgi kullanılarak ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="9fc6c-239">Elde edilen çağrılabilir taban çağrılabilir ile aynı sonuç türüne ve işlemler için aynı uzmanlıklarla aynı.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="9fc6c-240">Kısmi uygulamanın giriş türü, yalnızca belirtilen bağımsız değişkenler kaldırılmış olan özgün türdür.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="9fc6c-241">Kısmi uygulama oluştururken değişebilir bir değişken belirtilen bağımsız değişken olarak geçirilirse, değişkenin geçerli değeri kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="9fc6c-242">Değişkenin değerini daha sonra değiştirmek kısmi uygulamayı etkilemez.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="9fc6c-243">Örneğin, `Op` türü `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`varsa:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="9fc6c-244">`Op(5,(_,_))` `(((Qubit,Qubit), Double) => Unit is Adj)`tür ve bu nedenle `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="9fc6c-245">`Op(_,(_,1.0))` `((Int, (Qubit,Qubit)) => Unit is Adj)`türü vardır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="9fc6c-246">`Op(_,((q1,q2),_))` `((Int,Double) => Unit is Adj)`türü vardır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="9fc6c-247">Burada tek demet denklik 'i uyguladığımızda aklınızda olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="9fc6c-248">Kısmen uygulanmış çağrılabilir, derleyici tarafından çıkarsanamayan tür parametrelerine sahipse, bunun çağırma sitesinde sağlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="9fc6c-249">Kısmi uygulama belirtilmeyen tür parametrelerine sahip olamaz.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="9fc6c-250">Örneğin, `Op` türü `(('T1, Qubit, 'T1) => Unit : Adjoint)`varsa:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="9fc6c-251">Özyineleme</span><span class="sxs-lookup"><span data-stu-id="9fc6c-251">Recursion</span></span>

<span data-ttu-id="9fc6c-252">Q # callables 'in doğrudan veya dolaylı olarak özyinelemeli olmasına izin verilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="9fc6c-253">Diğer bir deyişle, bir işlem veya işlev kendisini çağırabilir veya çağrılabilir işlemi doğrudan veya dolaylı olarak çağıran başka bir çağrılabilir çağrısı sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="9fc6c-254">Ancak özyineleme kullanımı hakkında iki önemli yorum vardır:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="9fc6c-255">İşlemlerde özyineleme kullanımı, bazı iyileştirmelere engel olabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="9fc6c-256">Bu, algoritmanın yürütme süresi üzerinde önemli bir etkiye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="9fc6c-257">Gerçek bir hisse cihazında yürütme yaparken, yığın alanı sınırlı olabilir ve bu nedenle derin özyineleme bir çalışma zamanı hatasına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="9fc6c-258">Özellikle, Q # derleyicisi ve çalışma zamanı, kuyruk özyinelemeyi tanımlamaz ve iyileştirmez.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="9fc6c-259">Demet Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-259">Tuple Expressions</span></span>

<span data-ttu-id="9fc6c-260">Tanımlama grubu sabit değeri, `(` ve `)`içine alınmış, virgülle ayrılmış, uygun türdeki öğe ifadelerinin dizelerdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="9fc6c-261">Örneğin, `(1, One)` `(Int, Result)` bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="9fc6c-262">Değişmez değerler dışında, tek demet ifadeleri demet değerlerine, demet dizilerinin dizi öğelerine ve tanımlama grupları döndüren çağrılabilir çağırmaları olan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="9fc6c-263">Kullanıcı tanımlı tür Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="9fc6c-264">Kullanıcı tanımlı bir türün sabit değeri tür adından, ardından türün temel demet türünün bir tanımlama grubu değişmez değerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="9fc6c-265">Örneğin, `IntPair` `(Int, Int)`tabanlı kullanıcı tanımlı bir tür ise, `IntPair(2,3)` o türden geçerli bir sabit değer olacaktır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="9fc6c-266">Değişmez değerler dışında, Kullanıcı tanımlı bir türün tek ifadeleri, bu türün değerlerine, bu türden dizilerin dizi öğelerine ve bu türü döndüren çağrılabilir çağırmaları olan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="9fc6c-267">Ifade kaydırmayı geri al</span><span class="sxs-lookup"><span data-stu-id="9fc6c-267">Unwrap Expressions</span></span>

<span data-ttu-id="9fc6c-268">Q # içinde, Unwrap işleci sonda bir ünlem işaretiyle `!`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="9fc6c-269">Örneğin, `IntPair` temel alınan tür `(Int, Int)`sahip kullanıcı tanımlı bir tür ise ve `s` değeri `IntPair(2,3)`olan bir değişkense, `s!` `(2,3)`olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="9fc6c-270">Diğer Kullanıcı tanımlı türler bakımından tanımlanan Kullanıcı tanımlı türler için.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="9fc6c-271">Unwrap işleci yinelenebilir olabilir; Örneğin, `s!!`, `s`doğru sarmalanmamış değeri gösterir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="9fc6c-272">Bu nedenle, `WrappedPair` temel alınan türe sahip kullanıcı tanımlı bir tür `IntPair`ve `t` değeri `WrappedPair(IntPair(1,2))`olan bir değişkense, `t!!` `(1,2)`olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="9fc6c-273">`!` işleci, dizi dizini oluşturma ve dilimleme için `[]` dışındaki diğer işleçlerden daha yüksek önceliğe sahiptir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="9fc6c-274">`!` ve `[]` bağlama pozitif; diğer bir deyişle, `a[i]![3]` `((a[i])!)[3]`olarak okunmalıdır: `a``i`' th öğesini alın, sarmalayın ve sonra sarmalanmamış değerin 3. öğesini (bir dizi olması gerekir) alın.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="9fc6c-275">`!` işlecinin önceliği, belirgin bir etkiye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="9fc6c-276">Bir işlev veya işlem sarmalanmamış bir değer döndürürse, bağımsız değişken grubu, sarmalama yerine çağrıya bağlamak için işlev veya işlem çağrısının parantez içine alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="9fc6c-277">Örnek:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="9fc6c-278">Dizi Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-278">Array Expressions</span></span>

<span data-ttu-id="9fc6c-279">Dizi sabit değeri, `[` ve `]`içine alınmış, virgülle ayrılmış bir veya daha fazla öğe ifadesi dizisidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="9fc6c-280">Tüm öğeler aynı türle uyumlu olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="9fc6c-281">Ortak öğe türü bir işlem ya da işlev türü ise, tüm öğeler aynı giriş ve çıkış türlerine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="9fc6c-282">Dizinin öğe türü tüm öğeleri tarafından desteklenen tüm nesneleri destekleyecektir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="9fc6c-283">Örneğin, `Op1`, `Op2`ve `Op3` tümü `Qubit[] => Unit`, ancak `Op1` destekliyorsa `Adjoint`destekler ve `Op2` ikisini de destekler:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="9fc6c-284">`[Op1, Op2]`, `(Qubit[] => Unit)` işlemlerinin bir dizisidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="9fc6c-285">`[Op1, Op3]`, `(Qubit[] => Unit is Adj)` işlemlerinin bir dizisidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="9fc6c-286">`[Op2, Op3]`, `(Qubit[] => Unit is Ctl)` işlemlerinin bir dizisidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="9fc6c-287">Boş dizi değişmez değerlerine, `[]`izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="9fc6c-288">Bunun yerine, `★` uygun bir tür için yer tutucu olduğu `new ★[0]`kullanarak, istenen sıfır uzunluklu diziyi oluşturulmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="9fc6c-289">Aynı türde iki dizi verildiğinde, ikili `+` işleci iki dizinin birleşimi olan yeni bir dizi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="9fc6c-290">Örneğin, `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="9fc6c-291">Dizi oluşturma</span><span class="sxs-lookup"><span data-stu-id="9fc6c-291">Array Creation</span></span>

<span data-ttu-id="9fc6c-292">Bir tür ve `Int` ifadesi verildiğinde, `new` işleci verilen boyutun yeni bir dizisini ayırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="9fc6c-293">Örneğin `new Int[i+1]`, `i+1` öğeleriyle yeni bir `Int` dizisi ayırır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="9fc6c-294">Yeni bir dizinin öğeleri, türe bağlı bir varsayılan değere başlatılır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="9fc6c-295">Çoğu durumda bu bazı sıfır çeşitlerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="9fc6c-296">Varlıklara başvurular olan qubits ve callables için makul bir varsayılan değer yoktur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="9fc6c-297">Bu nedenle, bu tür için varsayılan, çalışma zamanı hatasına neden olmadan kullanılamayan geçersiz bir başvurudur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="9fc6c-298">Bu, C# veya Java gibi dillerde null başvuruya benzer.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="9fc6c-299">Qubits veya callables içeren diziler, öğeleri güvenle kullanılmadan önce varsayılan olmayan değerlerle düzgün başlatılmış olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="9fc6c-300">Uygun başlatma yordamları <xref:microsoft.quantum.arrays>bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="9fc6c-301">Her türün varsayılan değerleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-301">The default values for each type are:</span></span>

<span data-ttu-id="9fc6c-302">Tür</span><span class="sxs-lookup"><span data-stu-id="9fc6c-302">Type</span></span> | <span data-ttu-id="9fc6c-303">Varsayılan</span><span class="sxs-lookup"><span data-stu-id="9fc6c-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="9fc6c-304">_geçersiz qubit_</span><span class="sxs-lookup"><span data-stu-id="9fc6c-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="9fc6c-305">Boş Aralık `1..1..0`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="9fc6c-306">_geçersiz çağrılabilir_</span><span class="sxs-lookup"><span data-stu-id="9fc6c-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="9fc6c-307">Demet türleri, öğe öğesi tarafından başlatılmış.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="9fc6c-308">Sivri diziler</span><span class="sxs-lookup"><span data-stu-id="9fc6c-308">Jagged Arrays</span></span>

<span data-ttu-id="9fc6c-309">Bazen "dizi dizisi" olarak adlandırılan pürüzlü bir dizi, öğeleri dizi olan bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="9fc6c-310">Pürüzlü bir dizinin öğeleri farklı boyutlarda olabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="9fc6c-311">Aşağıdaki örnek, çarpma tablosunu temsil eden pürüzlü bir dizinin nasıl bildirilemeyeceğini ve başlatılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="9fc6c-312">Dizi dilimleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-312">Array Slices</span></span>

<span data-ttu-id="9fc6c-313">Bir dizi ifadesi ve bir `Range` ifadesi verildiğinde, `[` ve `]` dizi dilimi işleci kullanılarak yeni bir ifade oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="9fc6c-314">Yeni ifade, dizi ile aynı tür olur ve `Range`tarafından tanımlanan düzende `Range`öğeleri tarafından dizine alınmış dizi öğelerini içerir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="9fc6c-315">Örneğin, `a` bir `Double`s dizisine bağlıysa `a[3..-1..0]`, `a` ilk dört öğeyi içeren bir `Double[]` ifadedir ancak ters sırada `a`içinde görünürler.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="9fc6c-316">`Range` boşsa, sonuçta elde edilen dizi dilimi sıfır uzunluğunda olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="9fc6c-317">Dizi ifadesi basit bir tanımlayıcı değilse, dilimin dilimlemek için parantez içine alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="9fc6c-318">Örneğin, `a` ve `b` her ikisi de `Int`s dizilerinizde, birleştirme işleminden alınan bir dilim şöyle ifade edilir:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="9fc6c-319">Q # içindeki tüm diziler sıfır tabanlıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="9fc6c-320">Diğer bir deyişle, bir dizi `a` ilk öğesi her zaman `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="9fc6c-321">0,8 sürümümüzden başlayarak, Aralık Dilimleme için bağlamsal ifadeleri destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="9fc6c-322">Özellikle, Aralık başlangıç ve bitiş değerleri bir Aralık Dilimleme ifadesi bağlamında atlanabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="9fc6c-323">Bu durumda, derleyici aralığa yönelik istenen sınırlayıcıları çıkarması için aşağıdaki kuralları uygular.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="9fc6c-324">Örneğin, Aralık başlangıç değeri atlanırsa, çıkarılan başlangıç değeri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="9fc6c-325">bir adım belirtilmemişse veya belirtilen adım pozitifse sıfır ve</span><span class="sxs-lookup"><span data-stu-id="9fc6c-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="9fc6c-326">, belirtilen adım negatifse, dilimli dizinin uzunluğu eksi bir değer.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="9fc6c-327">Aralık bitiş değeri atlanırsa, çıkarılan bitiş değeri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="9fc6c-328">, bir adım belirtilmediyse veya belirtilen adım pozitif ise ve</span><span class="sxs-lookup"><span data-stu-id="9fc6c-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="9fc6c-329">, belirtilen adım negatifse sıfırdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="9fc6c-330">Dizi öğesi Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-330">Array Element Expressions</span></span>

<span data-ttu-id="9fc6c-331">Dizi ifadesi ve bir `Int` ifadesi verildiğinde, `[` ve `]` Array öğesi işleci kullanılarak yeni bir ifade oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="9fc6c-332">Yeni ifade, dizinin öğe türüyle aynı türde olacaktır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="9fc6c-333">Örneğin, `a` bir `Double`s dizisine bağlıysa `a[4]` `Double` bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="9fc6c-334">Dizi ifadesi basit bir tanımlayıcı değilse, bir öğe seçmek için parantez içine alınmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="9fc6c-335">Örneğin, `a` ve `b` her iki dizi `Int`de varsa, birleştirilmeden bir öğe şöyle ifade edilir:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="9fc6c-336">Q # içindeki tüm diziler sıfır tabanlıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="9fc6c-337">Diğer bir deyişle, bir dizi `a` ilk öğesi her zaman `a[0]`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="9fc6c-338">Kopyalama ve güncelleştirme Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="9fc6c-339">Yeni diziler, kopyalama ve güncelleştirme ifadeleri aracılığıyla mevcut olanlardan oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="9fc6c-340">Bir Copy-Update ifadesi, `expression1 w/ expression2 <- expression3``T`bir tür `T[]` `expression1` olması gereken form bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="9fc6c-341">İkinci `expression2`, `expression1` dizi ile karşılaştırıldığında değiştirilecek öğe (ler) in dizinlerini tanımlar ve `Int` türünden ya da `Range`türünde olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="9fc6c-342">`expression2` `Int`tür ise `expression3` `T`türünde olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="9fc6c-343">`expression2` `Range`tür ise `expression3` `T[]`türünde olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="9fc6c-344">Bir kopyalama ve güncelleştirme ifadesi `arr w/ idx <- value`, `idx`içindeki öğe (ler), `value`' de ayarlanan öğeler hariç, tüm öğeleri `arr`karşılık gelen öğeye ayarlanmış yeni bir dizi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="9fc6c-345">Örneğin, `arr` bir dizi `[0,1,2,3]`içeriyorsa,</span><span class="sxs-lookup"><span data-stu-id="9fc6c-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="9fc6c-346">`arr w/ 0 <- 10` dizi `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="9fc6c-347">`arr w/ 2 <- 10` dizi `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="9fc6c-348">`arr w/ 0..2..3 <- [10,12]` dizi `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="9fc6c-349">Kullanıcı tanımlı türlerde adlandırılmış öğeler için benzer ifadeler mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="9fc6c-350">Örneğin türü göz önünde bulundurun</span><span class="sxs-lookup"><span data-stu-id="9fc6c-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="9fc6c-351">`c`, `Complex(1.,-1.)`türünde değeri içeriyorsa `c w/ Re <- 0.`, `Complex(0.,-1.)`değerlendirilen `Complex` türünde bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="9fc6c-352">Koşullu Ifadeler</span><span class="sxs-lookup"><span data-stu-id="9fc6c-352">Conditional Expressions</span></span>

<span data-ttu-id="9fc6c-353">Aynı türde ve bir Boolean ifadesinin iki diğer ifadesi verildiğinde, koşullu ifade soru işareti `?` ve dikey çubuk `|`kullanılarak oluşturulmuş olabilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="9fc6c-354">Örneğin, `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="9fc6c-355">Bu örnekte, koşullu ifadenin değeri, `a==b` true ise ve false ise `d` `c` olacaktır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="9fc6c-356">İki ifade, aynı girişlere ve çıkışlara sahip olan ancak farklı komik desteği olan işlemlere göre değerlendirilemez.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="9fc6c-357">Bu durumda, koşullu ifadenin türü, her iki ifade tarafından desteklenen tüm semantikleri destekleyen bu giriş ve çıkışlarla bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="9fc6c-358">Örneğin, `Op1`, `Op2`ve `Op3` tümü `Qubit[]=>Unit`, ancak `Op1` destekliyorsa `Adjoint`destekler ve `Op2` ikisini de destekler:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="9fc6c-359">`flag ? Op1 | Op2` `(Qubit[] => Unit)` bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="9fc6c-360">`flag ? Op1 | Op3` `(Qubit[] => Unit is Adj)` bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="9fc6c-361">`flag ? Op2 | Op3` `(Qubit[] => Unit is Ctl)` bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="9fc6c-362">Olası iki sonuç ifadesi varsa, bir işlev veya işlem çağrısı içeriyorsa, bu çağrı yalnızca çağrının değeri olacak şekilde gerçekleşdiğinde olur.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="9fc6c-363">Örneğin, `a==b ? C(qs) | D(qs)`durumda, `a==b` true ise, `C` işlemi çağrılır ve false ise yalnızca `D` çağrılacaktır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="9fc6c-364">Bu, diğer dillerdeki kısa devre 'ya benzer.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="9fc6c-365">İşleç önceliği</span><span class="sxs-lookup"><span data-stu-id="9fc6c-365">Operator Precedence</span></span>

<span data-ttu-id="9fc6c-366">Tüm ikili işleçler `^`dışında sağ ilişkilendirilebilir.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="9fc6c-367">Parantez, `[` ve `]`, dizi Dilimleme ve dizin oluşturma için herhangi bir işleçten önce bağlayın.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="9fc6c-368">Komik `Adjoint` ve `Controlled` dizi dizinledikten sonra, diğer tüm işleçlerden önce bağlanır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="9fc6c-369">İşlem ve işlev çağırma parantezleri aynı zamanda herhangi bir işleçten önce, ancak dizi dizinlemesi ve komik bir şekilde bağlanır.</span><span class="sxs-lookup"><span data-stu-id="9fc6c-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="9fc6c-370">En yüksekten en düşüğe göre öncelik sırasına göre işleçler:</span><span class="sxs-lookup"><span data-stu-id="9fc6c-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="9fc6c-371">İşleç</span><span class="sxs-lookup"><span data-stu-id="9fc6c-371">Operator</span></span> | <span data-ttu-id="9fc6c-372">Sayısına</span><span class="sxs-lookup"><span data-stu-id="9fc6c-372">Arity</span></span> | <span data-ttu-id="9fc6c-373">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9fc6c-373">Description</span></span> | <span data-ttu-id="9fc6c-374">İşlenen türleri</span><span class="sxs-lookup"><span data-stu-id="9fc6c-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="9fc6c-375">Sondaki `!`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-375">trailing `!`</span></span> | <span data-ttu-id="9fc6c-376">Li</span><span class="sxs-lookup"><span data-stu-id="9fc6c-376">Unary</span></span> | <span data-ttu-id="9fc6c-377">Unwrap</span><span class="sxs-lookup"><span data-stu-id="9fc6c-377">Unwrap</span></span> | <span data-ttu-id="9fc6c-378">Kullanıcı tanımlı herhangi bir tür</span><span class="sxs-lookup"><span data-stu-id="9fc6c-378">Any user-defined type</span></span>
 <span data-ttu-id="9fc6c-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="9fc6c-380">Li</span><span class="sxs-lookup"><span data-stu-id="9fc6c-380">Unary</span></span> | <span data-ttu-id="9fc6c-381">Sayısal negatif, bit düzeyinde tamamlama, mantıksal değilleme</span><span class="sxs-lookup"><span data-stu-id="9fc6c-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="9fc6c-382">`Int` için `BigInt` `-`, `~~~`veya `Bool` için `Int`, `BigInt` veya `Double` `not`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="9fc6c-383">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-383">Binary</span></span> | <span data-ttu-id="9fc6c-384">Tamsayı güç</span><span class="sxs-lookup"><span data-stu-id="9fc6c-384">Integer power</span></span> | <span data-ttu-id="9fc6c-385">Taban için `Int` veya `BigInt` üs için `Int`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="9fc6c-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="9fc6c-387">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-387">Binary</span></span> | <span data-ttu-id="9fc6c-388">Bölme, çarpma, tamsayı mod</span><span class="sxs-lookup"><span data-stu-id="9fc6c-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="9fc6c-389">`*`için `/` ve `Int`, `BigInt` veya `%` için `Int`, `BigInt` veya `Double`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="9fc6c-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-390">`+`, `-`</span></span> | <span data-ttu-id="9fc6c-391">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-391">Binary</span></span> | <span data-ttu-id="9fc6c-392">Ekleme veya dize ve dizi birleştirme, çıkarma</span><span class="sxs-lookup"><span data-stu-id="9fc6c-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="9fc6c-393">`Int`, `BigInt` veya `Double`, ayrıca `+` için `String` veya herhangi bir dizi türü</span><span class="sxs-lookup"><span data-stu-id="9fc6c-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="9fc6c-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="9fc6c-395">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-395">Binary</span></span> | <span data-ttu-id="9fc6c-396">Sol SHIFT, sağa kaydırma</span><span class="sxs-lookup"><span data-stu-id="9fc6c-396">Left shift, right shift</span></span> | <span data-ttu-id="9fc6c-397">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="9fc6c-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="9fc6c-399">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-399">Binary</span></span> | <span data-ttu-id="9fc6c-400">Küçüktür, küçüktür veya eşittir, büyüktür, büyüktür veya eşittir karşılaştırmaları</span><span class="sxs-lookup"><span data-stu-id="9fc6c-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="9fc6c-401">`Int`, `BigInt` veya `Double`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="9fc6c-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-402">`==`, `!=`</span></span> | <span data-ttu-id="9fc6c-403">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-403">Binary</span></span> | <span data-ttu-id="9fc6c-404">eşit, eşit olmayan karşılaştırmalar</span><span class="sxs-lookup"><span data-stu-id="9fc6c-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="9fc6c-405">herhangi bir ilkel tür</span><span class="sxs-lookup"><span data-stu-id="9fc6c-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="9fc6c-406">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-406">Binary</span></span> | <span data-ttu-id="9fc6c-407">Bit düzeyinde AND</span><span class="sxs-lookup"><span data-stu-id="9fc6c-407">Bitwise AND</span></span> | <span data-ttu-id="9fc6c-408">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="9fc6c-409">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-409">Binary</span></span> | <span data-ttu-id="9fc6c-410">Bit düzeyinde XOR</span><span class="sxs-lookup"><span data-stu-id="9fc6c-410">Bitwise XOR</span></span> | <span data-ttu-id="9fc6c-411">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="9fc6c-412">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-412">Binary</span></span> | <span data-ttu-id="9fc6c-413">Bit düzeyinde OR</span><span class="sxs-lookup"><span data-stu-id="9fc6c-413">Bitwise OR</span></span> | <span data-ttu-id="9fc6c-414">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="9fc6c-415">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-415">Binary</span></span> | <span data-ttu-id="9fc6c-416">Mantıksal AND</span><span class="sxs-lookup"><span data-stu-id="9fc6c-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="9fc6c-417">ý</span><span class="sxs-lookup"><span data-stu-id="9fc6c-417">Binary</span></span> | <span data-ttu-id="9fc6c-418">Mantıksal OR</span><span class="sxs-lookup"><span data-stu-id="9fc6c-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="9fc6c-419">İkili/üçlü</span><span class="sxs-lookup"><span data-stu-id="9fc6c-419">Binary/Ternary</span></span> | <span data-ttu-id="9fc6c-420">Range işleci</span><span class="sxs-lookup"><span data-stu-id="9fc6c-420">Range operator</span></span> | `Int`
 <span data-ttu-id="9fc6c-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-421">`?` `|`</span></span> | <span data-ttu-id="9fc6c-422">Üçlü</span><span class="sxs-lookup"><span data-stu-id="9fc6c-422">Ternary</span></span> | <span data-ttu-id="9fc6c-423">Koşullu</span><span class="sxs-lookup"><span data-stu-id="9fc6c-423">Conditional</span></span> | <span data-ttu-id="9fc6c-424">Sol taraftaki `Bool`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="9fc6c-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="9fc6c-425">`w/` `<-`</span></span> | <span data-ttu-id="9fc6c-426">Üçlü</span><span class="sxs-lookup"><span data-stu-id="9fc6c-426">Ternary</span></span> | <span data-ttu-id="9fc6c-427">Kopyala ve Güncelleştir</span><span class="sxs-lookup"><span data-stu-id="9fc6c-427">Copy-and-update</span></span> | <span data-ttu-id="9fc6c-428">bkz. [kopyalama ve güncelleştirme ifadeleri](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="9fc6c-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
