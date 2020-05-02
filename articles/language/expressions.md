---
title: 'S # Ifadeleri'
description: Sabitleri, değişkenleri, işleçleri, işlemleri ve işlevleri soru-cevap olarak ifade olarak belirtme, başvurma ve birleştirme hakkında bilgi edinin.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.expressions
ms.openlocfilehash: 095be52af27f827f3e52d39a70702f50d6d59ee8
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82683921"
---
# <a name="expressions"></a><span data-ttu-id="db360-103">İfadeler</span><span class="sxs-lookup"><span data-stu-id="db360-103">Expressions</span></span>

## <a name="grouping"></a><span data-ttu-id="db360-104">Gruplandırma</span><span class="sxs-lookup"><span data-stu-id="db360-104">Grouping</span></span>

<span data-ttu-id="db360-105">Herhangi bir ifade verildiğinde, parantez içine alınmış aynı ifade aynı türde bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="db360-105">Given any expression, that same expression enclosed in parentheses is an expression of the same type.</span></span>
<span data-ttu-id="db360-106">`(7)` Örneğin, bir `Int` ifadedir `([1,2,3])` , dizi `Int`türünde bir ifadedir ve `((1,2))` türünde `(Int, Int)`bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="db360-106">For instance, `(7)` is an `Int` expression, `([1,2,3])` is an expression of type array of `Int`s, and `((1,2))` is an expression with type `(Int, Int)`.</span></span>

<span data-ttu-id="db360-107">[Tür modelinde](xref:microsoft.quantum.language.type-model#tuple-types) açıklanan basit değerler ve tek öğeli tanımlama grupları arasındaki denklik, Grup olarak ve `(6)` `(6)` tek öğeli tanımlama grubu arasındaki belirsizlik ortadan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="db360-107">The equivalence between simple values and single-element tuples described in [the type model](xref:microsoft.quantum.language.type-model#tuple-types) removes the ambiguity between `(6)` as a group and `(6)` as a single-element tuple.</span></span>

## <a name="symbols"></a><span data-ttu-id="db360-108">Simgeleri</span><span class="sxs-lookup"><span data-stu-id="db360-108">Symbols</span></span>

<span data-ttu-id="db360-109">Türünde `'T` bir değere göre veya atanan bir simgenin adı, türünde `'T`bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="db360-109">The name of a symbol bound or assigned to a value of type `'T` is an expression of type `'T`.</span></span>
<span data-ttu-id="db360-110">Örneğin, sembol `count` tamsayı değerine `5` `count` bağlıysa bir tamsayı ifadesidir.</span><span class="sxs-lookup"><span data-stu-id="db360-110">For instance, if the symbol `count` is bound to the integer value `5`, then `count` is an integer expression.</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="db360-111">Sayısal Ifadeler</span><span class="sxs-lookup"><span data-stu-id="db360-111">Numeric Expressions</span></span>

<span data-ttu-id="db360-112">Sayısal ifadeler, `Int` `BigInt`veya `Double`türündeki ifadelerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-112">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="db360-113">Diğer bir deyişle, tamsayı veya kayan noktalı sayılardır.</span><span class="sxs-lookup"><span data-stu-id="db360-113">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="db360-114">`Int`Soru-cevap "l" veya "L" gerekli olmadığında (veya izin verilmeyen), Q # içindeki değişmez değerler C# ' deki tamsayı değişmez değerler ile aynıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-114">`Int` literals in Q# are identical to integer literals in C#, except that no trailing "l" or "L" is required (or allowed).</span></span>
<span data-ttu-id="db360-115">Onaltılık ve ikili tamsayılar sırasıyla bir "0x" ve "0b" önekiyle desteklenir.</span><span class="sxs-lookup"><span data-stu-id="db360-115">Hexadecimal and binary integers are supported with a "0x" and "0b" prefix respectively.</span></span>

<span data-ttu-id="db360-116">`BigInt`Soru-cevap "l" veya "L" ile, Q # içindeki sabit değerler .NET 'teki büyük tamsayı dizeleriyle aynıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-116">`BigInt` literals in Q# are identical to big integer strings in .NET, with a trailing "l" or "L".</span></span>
<span data-ttu-id="db360-117">Onaltılık büyük tamsayılar bir "0x" öneki ile desteklenir.</span><span class="sxs-lookup"><span data-stu-id="db360-117">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="db360-118">Bu nedenle, tüm geçerli `BigInt` sabit değer kullanımları aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="db360-118">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="db360-119">`Double`Soru-cevap "d" veya "D" gerekli olmadığında (veya izin verilmeyen), Q # içindeki sabit değerler C# içindeki Double değişmez değerler ile aynıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-119">`Double` literals in Q# are identical to double literals in C#, except that no trailing "d" or "D" is required (or allowed).</span></span>

<span data-ttu-id="db360-120">Herhangi bir öğe türünün dizi ifadesi verildiğinde, `Int` bir ifade `Length` yerleşik işlev kullanılarak, dizi ifadesi parantez içine alınmış `(` ve `)`ile oluşturulmuş olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-120">Given an array expression of any element type, an `Int` expression may be formed using the `Length` built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="db360-121">Örneğin, `a` bir diziye `Length(a)` bağlıysa, bir tamsayı ifadesidir.</span><span class="sxs-lookup"><span data-stu-id="db360-121">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="db360-122">`b` , Tamsayıların `Int[][]` `Length(b)` dizilerindeki bir diziyse, içindeki `b`alt dizilerin sayısıdır ve `Length(b[1])` içindeki `b`ikinci alt dizideki tamsayıların sayısıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-122">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="db360-123">Aynı türde iki sayısal ifade verildiğinde, ikili `+`işleçler, `-` `*`,, ve `/` yeni bir sayısal ifade oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-123">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="db360-124">Yeni ifadenin türü, bileşen ifadelerinin türleriyle aynı olacaktır.</span><span class="sxs-lookup"><span data-stu-id="db360-124">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="db360-125">İki tamsayı ifadesi verildiğinde, ikili işleç `^` (güç) yeni bir tamsayı ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-125">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="db360-126">Benzer şekilde `^` , yeni bir Double ifadesi oluşturmak için iki çift ifade ile birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-126">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="db360-127">Son olarak `^` , solda büyük bir tamsayı ve yeni bir büyük tamsayı ifadesi oluşturmak için sağdaki bir tamsayı ile birlikte kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-127">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="db360-128">Bu durumda, ikinci parametrenin 32 bite sığması gerekir; Aksi takdirde, bir çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="db360-128">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="db360-129">İki tamsayı veya büyük tamsayı ifadesi verildiğinde `%` , (mod), `&&&` (bit düzeyinde and), `|||` (bit düzeyinde OR) veya `^^^` (bit düzeyinde xor) işleçleri kullanılarak yeni bir tamsayı veya büyük tamsayı ifadesi oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-129">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="db360-130">Sol tarafta bir tamsayı veya büyük tamsayı ifadesi ve sağ taraftaki bir tamsayı ifadesi verildiğinde, `<<<` (aritmetik sol SHIFT) veya `>>>` (aritmetik sağa kaydırma) işleçleri, sol ifadeyle aynı türde yeni bir ifade oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-130">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="db360-131">Kaydırma işleminin ikinci parametresi (SHIFT miktarı) sıfırdan büyük veya sıfıra eşit olmalıdır; negatif kaydırma miktarları için davranış tanımsızdır.</span><span class="sxs-lookup"><span data-stu-id="db360-131">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="db360-132">Her iki vardiya işlemi için de SHIFT miktarı 32 bite uyum sağlamalıdır; Aksi takdirde, bir çalışma zamanı hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="db360-132">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="db360-133">Kaydırılan sayı bir tamsayı ise, kaydırma miktarı yorumlanır `mod 64`; Yani, 1 ' in bir vardiyası ve 65 vardiyası aynı etkiye sahiptir.</span><span class="sxs-lookup"><span data-stu-id="db360-133">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="db360-134">Hem tamsayı hem de büyük tamsayı değerleri için, vardiyalar aritmetik değerlerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-134">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="db360-135">Negatif bir değeri sol veya sağ kaydırma, negatif bir sayı ile sonuçlanır.</span><span class="sxs-lookup"><span data-stu-id="db360-135">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="db360-136">Diğer bir deyişle, bir adım sola veya sağa kaydırma, sırasıyla 2 ile çarpılarak veya bölünerek tamamen aynıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-136">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="db360-137">Tamsayı bölme ve tamsayı mod, negatif sayılar için C# olarak aynı davranışı izler.</span><span class="sxs-lookup"><span data-stu-id="db360-137">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="db360-138">Diğer bir deyişle `a % b` , her zaman aynı işarete `a`sahip olur ve `b * (a / b) + a % b` her zaman eşit `a`olur.</span><span class="sxs-lookup"><span data-stu-id="db360-138">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="db360-139">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="db360-139">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="db360-140">5</span><span class="sxs-lookup"><span data-stu-id="db360-140">5</span></span> | <span data-ttu-id="db360-141">2</span><span class="sxs-lookup"><span data-stu-id="db360-141">2</span></span> | <span data-ttu-id="db360-142">2</span><span class="sxs-lookup"><span data-stu-id="db360-142">2</span></span> | <span data-ttu-id="db360-143">1</span><span class="sxs-lookup"><span data-stu-id="db360-143">1</span></span>
 <span data-ttu-id="db360-144">5</span><span class="sxs-lookup"><span data-stu-id="db360-144">5</span></span> | <span data-ttu-id="db360-145">-2</span><span class="sxs-lookup"><span data-stu-id="db360-145">-2</span></span> | <span data-ttu-id="db360-146">-2</span><span class="sxs-lookup"><span data-stu-id="db360-146">-2</span></span> | <span data-ttu-id="db360-147">1</span><span class="sxs-lookup"><span data-stu-id="db360-147">1</span></span>
 <span data-ttu-id="db360-148">-5</span><span class="sxs-lookup"><span data-stu-id="db360-148">-5</span></span> | <span data-ttu-id="db360-149">2</span><span class="sxs-lookup"><span data-stu-id="db360-149">2</span></span> | <span data-ttu-id="db360-150">-2</span><span class="sxs-lookup"><span data-stu-id="db360-150">-2</span></span> | <span data-ttu-id="db360-151">-1</span><span class="sxs-lookup"><span data-stu-id="db360-151">-1</span></span>
 <span data-ttu-id="db360-152">-5</span><span class="sxs-lookup"><span data-stu-id="db360-152">-5</span></span> | <span data-ttu-id="db360-153">-2</span><span class="sxs-lookup"><span data-stu-id="db360-153">-2</span></span> | <span data-ttu-id="db360-154">2</span><span class="sxs-lookup"><span data-stu-id="db360-154">2</span></span> | <span data-ttu-id="db360-155">-1</span><span class="sxs-lookup"><span data-stu-id="db360-155">-1</span></span>

<span data-ttu-id="db360-156">Büyük tamsayı bölme ve mod aynı şekilde çalışmaktadır.</span><span class="sxs-lookup"><span data-stu-id="db360-156">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="db360-157">Herhangi bir sayısal ifade verildiğinde, `-` birli işleç kullanılarak yeni bir ifade oluşturulmuş olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-157">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="db360-158">Yeni ifade, anayent ifadesiyle aynı türde olacaktır.</span><span class="sxs-lookup"><span data-stu-id="db360-158">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="db360-159">Herhangi bir tamsayı veya büyük tamsayı ifadesi verildiğinde, aynı türde yeni bir ifade `~~~` (bit düzeyinde tamamlayıcı) birli işleç kullanılarak oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-159">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="db360-160">Boole İfadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-160">Boolean Expressions</span></span>

<span data-ttu-id="db360-161">İki `Bool` değişmez değer de ve `true` ' `false`dir.</span><span class="sxs-lookup"><span data-stu-id="db360-161">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="db360-162">Aynı ilkel türdeki iki ifade verildiğinde, `==` ve `!=` ikili işleçler bir `Bool` ifade oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-162">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="db360-163">İki ifade eşitse ifade true, değilse false olur.</span><span class="sxs-lookup"><span data-stu-id="db360-163">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="db360-164">Kullanıcı tanımlı türlerin değerleri karşılaştırılamayabilir, yalnızca sarmalanmamış değerler karşılaştırılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-164">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="db360-165">Örneğin, "sarmalama" işlecini `!` kullanarak ( [Q # tür modeli sayfasında](xref:microsoft.quantum.language.type-model#user-defined-types)açıklanmıştır),</span><span class="sxs-lookup"><span data-stu-id="db360-165">For example, using the "unwrap" operator `!` (explained in the [Q# type model page](xref:microsoft.quantum.language.type-model#user-defined-types)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="db360-166">Değerler için `Qubit` eşitlik karşılaştırması kimlik eşitliğini; diğer bir deyişle, iki ifadenin aynı qubit 'i tanımlamasına bakılmaksızın.</span><span class="sxs-lookup"><span data-stu-id="db360-166">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="db360-167">İki qubits 'in durumu karşılaştırılmaz, erişilmez, ölçülemez veya bu karşılaştırma tarafından değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="db360-167">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="db360-168">Değerler için `Double` eşitlik karşılaştırması, yuvarlama etkileri nedeniyle yanıltıcı olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-168">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="db360-169">Örneğin, `49.0 * (1.0/49.0) != 1.0`.</span><span class="sxs-lookup"><span data-stu-id="db360-169">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="db360-170">Herhangi iki sayısal ifade verildiğinde,,, ve `>`ikili `<`işleçleri `>=`,, `<=` , ve ilk ifade sırasıyla sıfırdan büyük, küçüktür, büyüktür veya eşittir veya ikinci ifadeden daha küçük veya eşit olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-170">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="db360-171">İki Boolean ifade verildiğinde, `and` ve `or` ikili işleçler, iki ifadenin her ikisi de (her ikisi de veya her ikisi de) doğru olduğunda doğru olan yeni bir Boole ifadesi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-171">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="db360-172">Herhangi bir Boole ifadesi verildiğinde, `not` birli işleç yanlış olduğunda, doğru olan yeni bir Boole ifadesi oluşturmak için birli işleç kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-172">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="db360-173">Dize Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-173">String Expressions</span></span>

<span data-ttu-id="db360-174">Q #, `fail` deyimde ve `Log` standart işlevde dizelerin kullanılmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="db360-174">Q# allows strings to be used in the `fail` statement and the `Log` standard function.</span></span>

<span data-ttu-id="db360-175">Q # içindeki dizeler, değişmez değer veya enterpolasyonlu dizelerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-175">Strings in Q# are either literals or interpolated strings.</span></span>
<span data-ttu-id="db360-176">Dize sabit değerleri çoğu dilde basit dize sabit değerlerine benzer: çift tırnak içine alınmış bir Unicode karakter dizisi `"`.</span><span class="sxs-lookup"><span data-stu-id="db360-176">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="db360-177">Bir dizenin `\` içinde, arka eğik çizgi karakteri bir çift tırnak karakteriyle çıkmak ve yeni satır `\n`, satır başı olarak `\r`ve bir sekme olarak `\t`eklemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-177">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="db360-178">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="db360-178">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```

<span data-ttu-id="db360-179">Dize enterpolasyonları için Q # sözdizimi, C# 7,0 sözdiziminin bir alt kümesidir; S #, tam (çok satırlı) enterpolasyonlu dizeleri desteklemez.</span><span class="sxs-lookup"><span data-stu-id="db360-179">The Q# syntax for string interpolations is a subset of the C# 7.0 syntax; Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="db360-180">C# sözdizimi için bkz. [*enterpolasyonlu dizeler*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) .</span><span class="sxs-lookup"><span data-stu-id="db360-180">See [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings) for the C# syntax.</span></span>

<span data-ttu-id="db360-181">Enterpolasyonlu dize içindeki ifadeler, C# söz dizimini değil, Q # söz dizimini izler.</span><span class="sxs-lookup"><span data-stu-id="db360-181">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>
<span data-ttu-id="db360-182">Geçerli bir Q # ifadesi, enterpolasyonlu bir dizede görünebilir.</span><span class="sxs-lookup"><span data-stu-id="db360-182">Any valid Q# expression may appear in an interpolated string.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="db360-183">Qubit Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-183">Qubit Expressions</span></span>

<span data-ttu-id="db360-184">Tek `Qubit` ifadeler, `Qubit` `Qubit` dizilerin değerlerine veya dizi öğelerine bağlanan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-184">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="db360-185">`Qubit` Değişmez değer yok.</span><span class="sxs-lookup"><span data-stu-id="db360-185">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="db360-186">Pauli Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-186">Pauli Expressions</span></span>

<span data-ttu-id="db360-187">Dört `Pauli` değeri `PauliI` `PauliX` `PauliZ` `Pauli` ,,, ve, tüm geçerli ifadelerdir. `PauliY`</span><span class="sxs-lookup"><span data-stu-id="db360-187">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="db360-188">Bunun dışında, tek `Pauli` ifadeler, dizilere ait `Pauli` `Pauli` değerlere veya dizi öğelerine bağlanan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-188">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="db360-189">Sonuç Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-189">Result Expressions</span></span>

<span data-ttu-id="db360-190">İki `Result` değer `One` ve `Zero`, geçerli `Result` ifadelerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-190">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="db360-191">Bunun dışında, tek `Result` ifadeler, dizilere ait `Result` `Result` değerlere veya dizi öğelerine bağlanan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-191">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="db360-192">Özellikle, tamsayıyla `1`aynı `One` olmadığını ve aralarında doğrudan dönüşüm olmadığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="db360-192">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="db360-193">Aynı, ve `Zero` `0`için de geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="db360-193">The same is true for `Zero` and `0`.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="db360-194">Aralık Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-194">Range Expressions</span></span>

<span data-ttu-id="db360-195">, Ve `Int` `start` `step` `start` `start+step` `start+step+step` `stop` olmak üzere üç ifade verildiğinde, birinci öğesi olan bir Aralık ifadesi, ikinci öğe ise, üçüncü öğe, vb. olur. `stop` `start .. step .. stop`</span><span class="sxs-lookup"><span data-stu-id="db360-195">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="db360-196">Örneğin, pozitif ve `step` `stop < start`olduğunda bir Aralık boş olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-196">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="db360-197">Aralığın son öğesi, ve arasındaki fark, `stop` ve `start` `stop` arasında bir tamsayı `step`ise, diğer bir deyişle, Aralık her iki uçta da dahil olur.</span><span class="sxs-lookup"><span data-stu-id="db360-197">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="db360-198">`Int` Her iki ifade `start` de verildiğinde `stop`, `start .. stop` ve değerine eşit bir Aralık deyimidir `start .. 1 .. stop`.</span><span class="sxs-lookup"><span data-stu-id="db360-198">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="db360-199">Yukarıda, ' den `step` `stop` `start`küçük olsa bile, zımni + 1 olduğunu unutmayın. Böyle bir durumda, Aralık boştur.</span><span class="sxs-lookup"><span data-stu-id="db360-199">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="db360-200">Bazı örnek aralıklar şunlardır:</span><span class="sxs-lookup"><span data-stu-id="db360-200">Some example ranges are:</span></span>

- <span data-ttu-id="db360-201">`1..3`1, 2, 3 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-201">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="db360-202">`2..2..5`2, 4 aralığındadır.</span><span class="sxs-lookup"><span data-stu-id="db360-202">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="db360-203">`2..2..6`2, 4, 6 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-203">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="db360-204">`6..-2..2`6, 4, 2 aralığıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-204">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="db360-205">`2..1`boş aralıktır.</span><span class="sxs-lookup"><span data-stu-id="db360-205">`2..1` is the empty range.</span></span>
- <span data-ttu-id="db360-206">`2..6..7`Aralık 2 ' dir.</span><span class="sxs-lookup"><span data-stu-id="db360-206">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="db360-207">`2..2..1`boş aralıktır.</span><span class="sxs-lookup"><span data-stu-id="db360-207">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="db360-208">`1..-1..2`boş aralıktır.</span><span class="sxs-lookup"><span data-stu-id="db360-208">`1..-1..2` is the empty range.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="db360-209">Çağrılabilir Ifadeler</span><span class="sxs-lookup"><span data-stu-id="db360-209">Callable Expressions</span></span>

<span data-ttu-id="db360-210">Çağrılabilir sabit değer, derleme kapsamında tanımlanan bir işlemin veya işlevin adıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-210">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="db360-211">Örneğin, `X` standart kitaplık `X` işlemine başvuran bir işlem sabit değeri ve `Message` standart kitaplık `Message` işlevine başvuran bir işlev sabit değeri.</span><span class="sxs-lookup"><span data-stu-id="db360-211">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="db360-212">Bir işlem `Adjoint` functor destekliyorsa, bir işlem ifadesi `Adjoint op` olur.</span><span class="sxs-lookup"><span data-stu-id="db360-212">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="db360-213">Benzer şekilde, işlem `Controlled` functor 'ı destekliyorsa, bir işlem `Controlled op` ifadesi olur.</span><span class="sxs-lookup"><span data-stu-id="db360-213">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="db360-214">Bu ifadelerin türleri, [Funörler](xref:microsoft.quantum.language.type-model#functors)içinde belirtilmiştir.</span><span class="sxs-lookup"><span data-stu-id="db360-214">The types of these expressions are specified in [Functors](xref:microsoft.quantum.language.type-model#functors).</span></span>

<span data-ttu-id="db360-215">Funörler (`Adjoint` ve `Controlled`), ile `!` `[]`geri sarım operatörü ve dizi dizini oluşturma dışında diğer işleçlerden daha yakından bağlanır.</span><span class="sxs-lookup"><span data-stu-id="db360-215">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with `[]`.</span></span>
<span data-ttu-id="db360-216">Bu nedenle, işlemlerin kullanılan funları destekledikleri varsayılarak şunlar geçerlidir:</span><span class="sxs-lookup"><span data-stu-id="db360-216">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

<span data-ttu-id="db360-217">Çağrılabilir bir sabit değer olarak kullanılabilir, bir değişkene atamak veya başka bir çağrılabilir öğesine geçirmek için deyin.</span><span class="sxs-lookup"><span data-stu-id="db360-217">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="db360-218">Bu durumda, çağrılabilir tür parametrelerine sahipse, çağrılabilir değerin bir parçası olarak sağlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db360-218">In this case, if the callable has type parameters, they must be provided as part of the callable value.</span></span>
<span data-ttu-id="db360-219">Çağrılabilir bir değer belirtilmeyen tür parametrelerine sahip olamaz.</span><span class="sxs-lookup"><span data-stu-id="db360-219">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="db360-220">Örneğin, imzasına `'T1->Unit`sahip `Fun` bir işlevdir:</span><span class="sxs-lookup"><span data-stu-id="db360-220">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is Int->Unit.
SomeOtherFun(Fun<Double>);   // A Double->Unit is passed to SomeOtherFun.
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="db360-221">Çağrılabilir çağırma Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-221">Callable Invocation Expressions</span></span>

<span data-ttu-id="db360-222">Çağrılabilir bir (işlem veya işlev) ifadesi ve çağrılabilir öğesinin giriş türünün bir tanımlama grubu ifadesi verildiğinde, çağrılabilir ifadeye kayıt kümesi ifadesi eklenerek bir çağırma ifadesi oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-222">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="db360-223">Çağırma ifadesinin türü, çağrılabilir olan imzanın çıkış türüdür.</span><span class="sxs-lookup"><span data-stu-id="db360-223">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="db360-224">Örneğin, `Op` imzaya `((Int, Qubit) => Double)`sahip bir işlem ise, `Op(3, qubit1)` türünde `Double`bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="db360-224">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="db360-225">Benzer şekilde, `Sin` imzaya `(Double -> Double)`sahip bir işlevsiyse, `Sin(0.1)` türünde `Double`bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="db360-225">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="db360-226">Son olarak, `Builder` imza `(Int -> (Int -> Int))`içeren bir Işlevdir,, `Builder(3)` öğesinden Int 'e kadar bir işlevdir.</span><span class="sxs-lookup"><span data-stu-id="db360-226">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="db360-227">Çağrılabilir değerli bir ifadenin sonucunu çağırmak, çağrılabilir ifade etrafında fazladan bir çift parantez gerektirir.</span><span class="sxs-lookup"><span data-stu-id="db360-227">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="db360-228">Bu nedenle, önceki paragraftan çağırma `Builder` sonucunu çağırmak için doğru sözdizimi şöyledir:</span><span class="sxs-lookup"><span data-stu-id="db360-228">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="db360-229">Bir tür parametreli çağrılabilir çağırılırken, gerçek tür parametreleri açılı ayraç `<` içinde ve `>` çağrılabilir ifadeden sonra belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="db360-229">When invoking a type-parameterized callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="db360-230">Q # derleyicisi gerçek türleri çıkardığı için bu genellikle gereksizdir.</span><span class="sxs-lookup"><span data-stu-id="db360-230">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="db360-231">Bir tür parametreli bağımsız değişken belirtilmemişse, kısmi uygulama (aşağıya bakın) için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="db360-231">It is required for partial application (see below) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="db360-232">Ayrıca bazen farklı functor ile işlemleri bir çağrılabilir olarak geçirirken yararlı olur.</span><span class="sxs-lookup"><span data-stu-id="db360-232">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="db360-233">Örneğin, imzası `Func` `('T1, 'T2, 'T1) -> 'T2`varsa `Op1` `Op2` ve `(Qubit[] => Unit is Adj)`imza içeriyorsa ve `Op3` ilk bağımsız değişken `(Qubit[] => Unit)` `Func` `Op1` `Op2` olarak, ikinci olarak ve `Op3` üçüncü olarak çağırmak için imza varsa:</span><span class="sxs-lookup"><span data-stu-id="db360-233">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="db360-234">Tür belirtimi gereklidir çünkü `Op3` ve `Op1` farklı türlere sahip olur, bu nedenle derleyici bunu belirtim olmadan belirsiz olarak değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="db360-234">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>

### <a name="partial-application"></a><span data-ttu-id="db360-235">Kısmi uygulama</span><span class="sxs-lookup"><span data-stu-id="db360-235">Partial Application</span></span>

<span data-ttu-id="db360-236">Çağrılabilir bir ifade verildiğinde, çağrılabilir bir bağımsız değişkenlerin alt kümesini sağlayarak yeni bir çağrılabilir oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-236">Given a callable expression, a new callable may be created by providing a subset of the arguments to the callable.</span></span>
<span data-ttu-id="db360-237">Buna _kısmi uygulama_denir.</span><span class="sxs-lookup"><span data-stu-id="db360-237">This is called _partial application_.</span></span>

<span data-ttu-id="db360-238">Q # ' da, kısmen uygulanan çağrılabilir bir normal çağırma ifadesi yazılarak, ancak belirtilmeyen bağımsız değişkenler için alt çizgi `_`kullanılarak ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="db360-238">In Q#, a partially applied callable is expressed by writing a normal invocation expression, but using an underscore, `_`, for the unspecified arguments.</span></span>
<span data-ttu-id="db360-239">Elde edilen çağrılabilir taban çağrılabilir ile aynı sonuç türüne ve işlemler için aynı uzmanlıklarla aynı.</span><span class="sxs-lookup"><span data-stu-id="db360-239">The resulting callable has the same result type as the base callable, and the same specializations for operations.</span></span>
<span data-ttu-id="db360-240">Kısmi uygulamanın giriş türü, yalnızca belirtilen bağımsız değişkenler kaldırılmış olan özgün türdür.</span><span class="sxs-lookup"><span data-stu-id="db360-240">The input type of the partial application is simply the original type with the specified arguments removed.</span></span>

<span data-ttu-id="db360-241">Kısmi uygulama oluştururken değişebilir bir değişken belirtilen bağımsız değişken olarak geçirilirse, değişkenin geçerli değeri kullanılır.</span><span class="sxs-lookup"><span data-stu-id="db360-241">If a mutable variable is passed as a specified argument when creating a partial application, the current value of the variable is used.</span></span>
<span data-ttu-id="db360-242">Değişkenin değerini daha sonra değiştirmek kısmi uygulamayı etkilemez.</span><span class="sxs-lookup"><span data-stu-id="db360-242">Changing the value of the variable afterward will not impact the partial application.</span></span>

<span data-ttu-id="db360-243">Örneğin, şunu `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`içeriyorsa `Op` :</span><span class="sxs-lookup"><span data-stu-id="db360-243">For example, if `Op` has type `((Int, ((Qubit, Qubit), Double)) => Unit is Adj)`:</span></span>

- <span data-ttu-id="db360-244">`Op(5,(_,_))`türüne `(((Qubit,Qubit), Double) => Unit is Adj)`sahiptir ve bu nedenle `Op(5,_)`.</span><span class="sxs-lookup"><span data-stu-id="db360-244">`Op(5,(_,_))` has type `(((Qubit,Qubit), Double) => Unit is Adj)`, and so has `Op(5,_)`.</span></span>
- <span data-ttu-id="db360-245">`Op(_,(_,1.0))`türü `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="db360-245">`Op(_,(_,1.0))` has type `((Int, (Qubit,Qubit)) => Unit is Adj)`.</span></span>
- <span data-ttu-id="db360-246">`Op(_,((q1,q2),_))`türü `((Int,Double) => Unit is Adj)`.</span><span class="sxs-lookup"><span data-stu-id="db360-246">`Op(_,((q1,q2),_))` has type `((Int,Double) => Unit is Adj)`.</span></span>
   <span data-ttu-id="db360-247">Burada tek demet denklik 'i uyguladığımızda aklınızda olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="db360-247">Note that we have applied singleton tuple equivalence here.</span></span>

<span data-ttu-id="db360-248">Kısmen uygulanmış çağrılabilir, derleyici tarafından çıkarsanamayan tür parametrelerine sahipse, bunun çağırma sitesinde sağlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db360-248">If the partially-applied callable has type parameters that cannot be inferred by the compiler, they must be provided at the invocation site.</span></span>
<span data-ttu-id="db360-249">Kısmi uygulama belirtilmeyen tür parametrelerine sahip olamaz.</span><span class="sxs-lookup"><span data-stu-id="db360-249">The partial application cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="db360-250">Örneğin, şunu `(('T1, Qubit, 'T1) => Unit : Adjoint)`içeriyorsa `Op` :</span><span class="sxs-lookup"><span data-stu-id="db360-250">For example, if `Op` has type `(('T1, Qubit, 'T1) => Unit : Adjoint)`:</span></span>

```qsharp
let f1 = Op<Int>(_, qb, _); // f1 has type ((Int,Int) => Unit is Adj)
let f2 = Op(5, qb, _);      // f2 has type (Int => Unit is Adj)
let f3 = Op(_,qb, _);       // f3 generates a compilation error
```

### <a name="recursion"></a><span data-ttu-id="db360-251">Özyineleme</span><span class="sxs-lookup"><span data-stu-id="db360-251">Recursion</span></span>

<span data-ttu-id="db360-252">Q # callables 'in doğrudan veya dolaylı olarak özyinelemeli olmasına izin verilir.</span><span class="sxs-lookup"><span data-stu-id="db360-252">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="db360-253">Diğer bir deyişle, bir işlem veya işlev kendisini çağırabilir veya çağrılabilir işlemi doğrudan veya dolaylı olarak çağıran başka bir çağrılabilir çağrısı sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-253">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="db360-254">Ancak özyineleme kullanımı hakkında iki önemli yorum vardır:</span><span class="sxs-lookup"><span data-stu-id="db360-254">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="db360-255">İşlemlerde özyineleme kullanımı, bazı iyileştirmelere engel olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-255">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="db360-256">Bu, algoritmanın yürütme süresi üzerinde önemli bir etkiye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-256">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="db360-257">Gerçek bir hisse cihazında yürütme yaparken, yığın alanı sınırlı olabilir ve bu nedenle derin özyineleme bir çalışma zamanı hatasına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-257">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="db360-258">Özellikle, Q # derleyicisi ve çalışma zamanı, kuyruk özyinelemeyi tanımlamaz ve iyileştirmez.</span><span class="sxs-lookup"><span data-stu-id="db360-258">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="db360-259">Demet Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-259">Tuple Expressions</span></span>

<span data-ttu-id="db360-260">Tanımlama grubu değişmez değeri, ve `(` `)`' de bulunan, virgülle ayrılmış şekilde, uygun türdeki öğe ifadelerinin dizelerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-260">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="db360-261">Örneğin, `(1, One)` bir `(Int, Result)` ifadedir.</span><span class="sxs-lookup"><span data-stu-id="db360-261">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="db360-262">Değişmez değerler dışında, tek demet ifadeleri demet değerlerine, demet dizilerinin dizi öğelerine ve tanımlama grupları döndüren çağrılabilir çağırmaları olan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-262">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="db360-263">Kullanıcı tanımlı tür Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-263">User-Defined Type Expressions</span></span>

<span data-ttu-id="db360-264">Kullanıcı tanımlı bir türün sabit değeri tür adından, ardından türün temel demet türünün bir tanımlama grubu değişmez değerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="db360-264">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="db360-265">Örneğin, `IntPair` temelli Kullanıcı tanımlı bir tür ise `(Int, Int)`, `IntPair(2,3)` bu türün geçerli bir sabit değeri olur.</span><span class="sxs-lookup"><span data-stu-id="db360-265">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2,3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="db360-266">Değişmez değerler dışında, Kullanıcı tanımlı bir türün tek ifadeleri, bu türün değerlerine, bu türden dizilerin dizi öğelerine ve bu türü döndüren çağrılabilir çağırmaları olan sembollerdir.</span><span class="sxs-lookup"><span data-stu-id="db360-266">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="db360-267">Ifade kaydırmayı geri al</span><span class="sxs-lookup"><span data-stu-id="db360-267">Unwrap Expressions</span></span>

<span data-ttu-id="db360-268">Q # içinde, Unwrap işleci sondaki bir ünlem işaretidir `!`.</span><span class="sxs-lookup"><span data-stu-id="db360-268">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="db360-269">Örneğin `IntPair` , temel alınan `(Int, Int)`türe sahip kullanıcı tanımlı bir türdür ve `s` değeri `IntPair(2,3)`olan bir değişkense, daha sonra `s!` olur. `(2,3)`</span><span class="sxs-lookup"><span data-stu-id="db360-269">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2,3)`, then `s!` would be `(2,3)`.</span></span>

<span data-ttu-id="db360-270">Diğer Kullanıcı tanımlı türler bakımından tanımlanan Kullanıcı tanımlı türler için.</span><span class="sxs-lookup"><span data-stu-id="db360-270">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="db360-271">Unwrap işleci yinelenebilir olabilir; Örneğin, `s!!` paketlenmiş, sarmalanmamış değeri gösterir `s`.</span><span class="sxs-lookup"><span data-stu-id="db360-271">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="db360-272">Bu nedenle, `WrappedPair` temel `IntPair`alınan türe sahip kullanıcı tanımlı bir türdür ve `t` değeri `WrappedPair(IntPair(1,2))` `t!!` olan bir değişkense, olur. `(1,2)`</span><span class="sxs-lookup"><span data-stu-id="db360-272">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="db360-273">İşleç `!` , dizi dizini oluşturma ve dilimleme `[]` için dışındaki diğer işleçlerden daha yüksek önceliğe sahiptir.</span><span class="sxs-lookup"><span data-stu-id="db360-273">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="db360-274">`!`ve `[]` , pozitif bağlama; diğer bir deyişle `a[i]![3]` , şöyle `((a[i])!)[3]`okunmalıdır: `i`' th öğesini alın `a`, sarmalayın ve sonra sarmalanmamış değerin 3. öğesini (bir dizi olması gerekir) alın.</span><span class="sxs-lookup"><span data-stu-id="db360-274">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="db360-275">`!` İşlecin önceliği belirgin olmayan bir etkiye sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-275">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="db360-276">Bir işlev veya işlem sarmalanmamış bir değer döndürürse, bağımsız değişken grubu, sarmalama yerine çağrıya bağlamak için işlev veya işlem çağrısının parantez içine alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db360-276">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="db360-277">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="db360-277">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="db360-278">Dizi Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-278">Array Expressions</span></span>

<span data-ttu-id="db360-279">Dizi değişmez değeri, virgülle ayrılmış bir veya daha fazla öğe ifadesinin sırasıdır `[` ve. `]`</span><span class="sxs-lookup"><span data-stu-id="db360-279">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="db360-280">Tüm öğeler aynı türle uyumlu olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-280">All elements must be compatible with the same type.</span></span>

<span data-ttu-id="db360-281">Ortak öğe türü bir işlem ya da işlev türü ise, tüm öğeler aynı giriş ve çıkış türlerine sahip olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-281">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="db360-282">Dizinin öğe türü tüm öğeleri tarafından desteklenen tüm nesneleri destekleyecektir.</span><span class="sxs-lookup"><span data-stu-id="db360-282">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="db360-283">Örneğin,, ve `Op1`hepsi `Op2` `Op3` `Qubit[] => Unit` `Op1` ise,, ve her ikisini de `Adjoint`destekler `Op2` , `Controlled`destekler ve `Op3` destekler:</span><span class="sxs-lookup"><span data-stu-id="db360-283">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="db360-284">`[Op1, Op2]`, bir dizi `(Qubit[] => Unit)` işlemden oluşur.</span><span class="sxs-lookup"><span data-stu-id="db360-284">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="db360-285">`[Op1, Op3]`, bir dizi `(Qubit[] => Unit is Adj)` işlemden oluşur.</span><span class="sxs-lookup"><span data-stu-id="db360-285">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="db360-286">`[Op2, Op3]`, bir dizi `(Qubit[] => Unit is Ctl)` işlemden oluşur.</span><span class="sxs-lookup"><span data-stu-id="db360-286">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="db360-287">Boş dizi değişmez `[]`değerlerine izin verilmez.</span><span class="sxs-lookup"><span data-stu-id="db360-287">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="db360-288">Bunun yerine `new ★[0]`,, `★` uygun bir tür için yer tutucu olarak olduğu gibi, istenen sıfır uzunluklu diziyi oluşturulmasına izin verir.</span><span class="sxs-lookup"><span data-stu-id="db360-288">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>

<span data-ttu-id="db360-289">Aynı türde iki dizi verildiğinde, ikili `+` işleç iki dizinin birleşimi olan yeni bir dizi oluşturmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-289">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="db360-290">Örneğin, `[1,2,3] + [4,5,6]` `[1,2,3,4,5,6]`.</span><span class="sxs-lookup"><span data-stu-id="db360-290">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="db360-291">Dizi oluşturma</span><span class="sxs-lookup"><span data-stu-id="db360-291">Array Creation</span></span>

<span data-ttu-id="db360-292">Bir tür ve `Int` ifade verildiğinde, `new` işleç verilen boyutun yeni bir dizisini ayırmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-292">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="db360-293">Örneğin, `new Int[i+1]` öğeleri içeren `Int` `i+1` yeni bir dizi ayırır.</span><span class="sxs-lookup"><span data-stu-id="db360-293">For instance, `new Int[i+1]` would allocate a new `Int` array with `i+1` elements.</span></span>

<span data-ttu-id="db360-294">Yeni bir dizinin öğeleri, türe bağlı bir varsayılan değere başlatılır.</span><span class="sxs-lookup"><span data-stu-id="db360-294">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="db360-295">Çoğu durumda bu bazı sıfır çeşitlerinden oluşur.</span><span class="sxs-lookup"><span data-stu-id="db360-295">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="db360-296">Varlıklara başvurular olan qubits ve callables için makul bir varsayılan değer yoktur.</span><span class="sxs-lookup"><span data-stu-id="db360-296">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="db360-297">Bu nedenle, bu tür için varsayılan, çalışma zamanı hatasına neden olmadan kullanılamayan geçersiz bir başvurudur.</span><span class="sxs-lookup"><span data-stu-id="db360-297">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="db360-298">Bu, C# veya Java gibi dillerde null başvuruya benzer.</span><span class="sxs-lookup"><span data-stu-id="db360-298">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="db360-299">Qubits veya callables içeren diziler, öğeleri güvenle kullanılmadan önce varsayılan olmayan değerlerle düzgün başlatılmış olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-299">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="db360-300">İçin uygun başlatma yordamları bulunabilir <xref:microsoft.quantum.arrays>.</span><span class="sxs-lookup"><span data-stu-id="db360-300">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="db360-301">Her türün varsayılan değerleri şunlardır:</span><span class="sxs-lookup"><span data-stu-id="db360-301">The default values for each type are:</span></span>

<span data-ttu-id="db360-302">Tür</span><span class="sxs-lookup"><span data-stu-id="db360-302">Type</span></span> | <span data-ttu-id="db360-303">Varsayılan</span><span class="sxs-lookup"><span data-stu-id="db360-303">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="db360-304">_geçersiz qubit_</span><span class="sxs-lookup"><span data-stu-id="db360-304">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="db360-305">Boş Aralık,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="db360-305">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="db360-306">_geçersiz çağrılabilir_</span><span class="sxs-lookup"><span data-stu-id="db360-306">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="db360-307">Demet türleri, öğe öğesi tarafından başlatılmış.</span><span class="sxs-lookup"><span data-stu-id="db360-307">Tuple types are initialized element-by-element.</span></span>


### <a name="jagged-arrays"></a><span data-ttu-id="db360-308">Düzensiz Diziler</span><span class="sxs-lookup"><span data-stu-id="db360-308">Jagged Arrays</span></span>

<span data-ttu-id="db360-309">Bazen "dizi dizisi" olarak adlandırılan pürüzlü bir dizi, öğeleri dizi olan bir dizidir.</span><span class="sxs-lookup"><span data-stu-id="db360-309">A jagged array, sometimes called an "array of arrays", is an array whose elements are arrays.</span></span> <span data-ttu-id="db360-310">Pürüzlü bir dizinin öğeleri farklı boyutlarda olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-310">The elements of a jagged array can be of different sizes.</span></span> <span data-ttu-id="db360-311">Aşağıdaki örnek, çarpma tablosunu temsil eden pürüzlü bir dizinin nasıl bildirilemeyeceğini ve başlatılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="db360-311">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

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


### <a name="array-slices"></a><span data-ttu-id="db360-312">Dizi dilimleri</span><span class="sxs-lookup"><span data-stu-id="db360-312">Array Slices</span></span>

<span data-ttu-id="db360-313">Bir dizi ifadesi ve bir `Range` ifade verildiğinde, `[` ve `]` dizi dilimi işleci kullanılarak yeni bir ifade oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-313">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="db360-314">Yeni ifade, dizisiyle aynı türde olur ve tarafından tanımlanan sırada öğesi `Range`tarafından dizin oluşturulan dizi öğelerini içerir. `Range`</span><span class="sxs-lookup"><span data-stu-id="db360-314">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="db360-315">Örneğin, `a` bir dizi bir diziyle `Double`ilişkiliyse, `a[3..-1..0]` ' ın ilk dört öğesini, `Double[]` `a` ancak içinde `a`göründükleri şekilde ters sırada içeren bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="db360-315">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="db360-316">`Range` Boşsa, sonuçta elde edilen dizi dilimi sıfır uzunluğunda olur.</span><span class="sxs-lookup"><span data-stu-id="db360-316">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="db360-317">Dizi ifadesi basit bir tanımlayıcı değilse, dilimin dilimlemek için parantez içine alınması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db360-317">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="db360-318">Örneğin, ve `a` `b` her iki dizisise `Int`, birleştirilmeden bir dilim şöyle ifade edilir:</span><span class="sxs-lookup"><span data-stu-id="db360-318">For instance, if `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

<span data-ttu-id="db360-319">Q # içindeki tüm diziler sıfır tabanlıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-319">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="db360-320">Diğer bir deyişle, bir dizinin `a` ilk öğesi her zaman `a[0]`olur.</span><span class="sxs-lookup"><span data-stu-id="db360-320">That is, the first element of an array `a` is always `a[0]`.</span></span>

<span data-ttu-id="db360-321">0,8 sürümümüzden başlayarak, Aralık Dilimleme için bağlamsal ifadeleri destekliyoruz.</span><span class="sxs-lookup"><span data-stu-id="db360-321">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="db360-322">Özellikle, Aralık başlangıç ve bitiş değerleri bir Aralık Dilimleme ifadesi bağlamında atlanabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-322">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="db360-323">Bu durumda, derleyici aralığa yönelik istenen sınırlayıcıları çıkarması için aşağıdaki kuralları uygular.</span><span class="sxs-lookup"><span data-stu-id="db360-323">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="db360-324">Örneğin, Aralık başlangıç değeri atlanırsa, çıkarılan başlangıç değeri</span><span class="sxs-lookup"><span data-stu-id="db360-324">For example, if the range start value is omitted, then the inferred start value</span></span> 
- <span data-ttu-id="db360-325">bir adım belirtilmemişse veya belirtilen adım pozitifse sıfır ve</span><span class="sxs-lookup"><span data-stu-id="db360-325">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="db360-326">, belirtilen adım negatifse, dilimli dizinin uzunluğu eksi bir değer.</span><span class="sxs-lookup"><span data-stu-id="db360-326">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="db360-327">Aralık bitiş değeri atlanırsa, çıkarılan bitiş değeri</span><span class="sxs-lookup"><span data-stu-id="db360-327">If the range end value is omitted, then the inferred end value</span></span> 
- <span data-ttu-id="db360-328">, bir adım belirtilmediyse veya belirtilen adım pozitif ise ve</span><span class="sxs-lookup"><span data-stu-id="db360-328">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="db360-329">, belirtilen adım negatifse sıfırdır.</span><span class="sxs-lookup"><span data-stu-id="db360-329">is zero if the specified step is negative.</span></span> 

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

## <a name="array-element-expressions"></a><span data-ttu-id="db360-330">Dizi öğesi Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-330">Array Element Expressions</span></span>

<span data-ttu-id="db360-331">Bir dizi ifadesi ve bir `Int` ifade verildiğinde, `[` ve `]` dizi öğesi işleci kullanılarak yeni bir ifade oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-331">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="db360-332">Yeni ifade, dizinin öğe türüyle aynı türde olacaktır.</span><span class="sxs-lookup"><span data-stu-id="db360-332">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="db360-333">Örneğin, `a` bir dizi `Double`s `a[4]` öğesine bağlıysa, bir `Double` ifadedir.</span><span class="sxs-lookup"><span data-stu-id="db360-333">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="db360-334">Dizi ifadesi basit bir tanımlayıcı değilse, bir öğe seçmek için parantez içine alınmalıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-334">If the array expression is not a simple identifier, it must be enclosed it parentheses in order to select an element.</span></span>
<span data-ttu-id="db360-335">Örneğin, ve `a` `b` öğelerinin her ikisi de `Int`varsa, birleştirilmeden bir öğe şöyle ifade edilir:</span><span class="sxs-lookup"><span data-stu-id="db360-335">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[13]
```

<span data-ttu-id="db360-336">Q # içindeki tüm diziler sıfır tabanlıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-336">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="db360-337">Diğer bir deyişle, bir dizinin `a` ilk öğesi her zaman `a[0]`olur.</span><span class="sxs-lookup"><span data-stu-id="db360-337">That is, the first element of an array `a` is always `a[0]`.</span></span>


## <a name="copy-and-update-expressions"></a><span data-ttu-id="db360-338">Kopyalama ve güncelleştirme Ifadeleri</span><span class="sxs-lookup"><span data-stu-id="db360-338">Copy-and-Update Expressions</span></span>

<span data-ttu-id="db360-339">Yeni diziler, kopyalama ve güncelleştirme ifadeleri aracılığıyla mevcut olanlardan oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-339">New arrays can be created from existing ones via copy-and-update expressions.</span></span>
<span data-ttu-id="db360-340">Bir Copy-Update ifadesi `expression1 w/ expression2 <- expression3`formun bir ifadesidir, burada `expression1` bir tür `T[]` `T`için tür olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db360-340">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span> <span data-ttu-id="db360-341">İkincisi `expression2` , içindeki `expression1` diziye kıyasla değiştirilecek öğe dizinlerini tanımlar ve türünden `Int` ya da türünde `Range`olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="db360-341">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span> <span data-ttu-id="db360-342">`expression2` Türünde `Int`ise, `expression3` türünde `T`olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db360-342">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="db360-343">`expression2` Türünde `Range`ise, `expression3` türünde `T[]`olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="db360-343">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="db360-344">Bir Copy-Update `arr w/ idx <- value` ifadesi, ' deki öğe (ler) `arr` `idx`i olarak ayarlanan öğeler hariç, içindeki öğesine karşılık gelen öğeye ayarlanmış olan yeni bir dizi oluşturur. `value`</span><span class="sxs-lookup"><span data-stu-id="db360-344">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="db360-345">Örneğin, bir dizi `arr` `[0,1,2,3]`içeriyorsa,</span><span class="sxs-lookup"><span data-stu-id="db360-345">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="db360-346">`arr w/ 0 <- 10`dizi `[10,1,2,3]`.</span><span class="sxs-lookup"><span data-stu-id="db360-346">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="db360-347">`arr w/ 2 <- 10`dizi `[0,1,10,3]`.</span><span class="sxs-lookup"><span data-stu-id="db360-347">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="db360-348">`arr w/ 0..2..3 <- [10,12]`dizi `[10,1,12,3]`.</span><span class="sxs-lookup"><span data-stu-id="db360-348">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

<span data-ttu-id="db360-349">Kullanıcı tanımlı türlerde adlandırılmış öğeler için benzer ifadeler mevcuttur.</span><span class="sxs-lookup"><span data-stu-id="db360-349">Similar expressions exist for named items in user-defined types.</span></span> <span data-ttu-id="db360-350">Örneğin türü göz önünde bulundurun</span><span class="sxs-lookup"><span data-stu-id="db360-350">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="db360-351">Türü `c` `Complex(1.,-1.)`değerini içeriyorsa,, `c w/ Re <- 0.` olarak `Complex` `Complex(0.,-1.)`değerlendirilen türünde bir ifadedir.</span><span class="sxs-lookup"><span data-stu-id="db360-351">If `c` contains the value of type `Complex(1.,-1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0.,-1.)`.</span></span>

## <a name="conditional-expressions"></a><span data-ttu-id="db360-352">Koşullu Ifadeler</span><span class="sxs-lookup"><span data-stu-id="db360-352">Conditional Expressions</span></span>

<span data-ttu-id="db360-353">Aynı türde ve bir Boolean ifadesinin iki diğer ifadesi verildiğinde, koşullu ifade soru işareti `?` ve dikey çubuk `|`kullanılarak oluşturulmuş olabilir.</span><span class="sxs-lookup"><span data-stu-id="db360-353">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="db360-354">Örneğin, `a==b ? c | d`.</span><span class="sxs-lookup"><span data-stu-id="db360-354">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="db360-355">Bu örnekte, koşullu ifadenin değeri true `c` `a==b` `d` , ise false ise olur.</span><span class="sxs-lookup"><span data-stu-id="db360-355">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

<span data-ttu-id="db360-356">İki ifade, aynı girişlere ve çıkışlara sahip olan ancak farklı komik desteği olan işlemlere göre değerlendirilemez.</span><span class="sxs-lookup"><span data-stu-id="db360-356">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="db360-357">Bu durumda, koşullu ifadenin türü, her iki ifade tarafından desteklenen tüm semantikleri destekleyen bu giriş ve çıkışlarla bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="db360-357">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="db360-358">Örneğin,, ve `Op1`hepsi `Op2` `Op3` `Qubit[]=>Unit` `Op1` ise,, ve her ikisini de `Adjoint`destekler `Op2` , `Controlled`destekler ve `Op3` destekler:</span><span class="sxs-lookup"><span data-stu-id="db360-358">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="db360-359">`flag ? Op1 | Op2`bir `(Qubit[] => Unit)` işlemdir.</span><span class="sxs-lookup"><span data-stu-id="db360-359">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="db360-360">`flag ? Op1 | Op3`bir `(Qubit[] => Unit is Adj)` işlemdir.</span><span class="sxs-lookup"><span data-stu-id="db360-360">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="db360-361">`flag ? Op2 | Op3`bir `(Qubit[] => Unit is Ctl)` işlemdir.</span><span class="sxs-lookup"><span data-stu-id="db360-361">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="db360-362">Olası iki sonuç ifadesi varsa, bir işlev veya işlem çağrısı içeriyorsa, bu çağrı yalnızca çağrının değeri olacak şekilde gerçekleşdiğinde olur.</span><span class="sxs-lookup"><span data-stu-id="db360-362">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="db360-363">Örneğin `a==b ? C(qs) | D(qs)`, bu durumda `a==b` , true ise `C` işlem çağrılacaktır ve false ise yalnızca `D` çağrılacaktır.</span><span class="sxs-lookup"><span data-stu-id="db360-363">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="db360-364">Bu, diğer dillerdeki kısa devre 'ya benzer.</span><span class="sxs-lookup"><span data-stu-id="db360-364">This is similar to short-circuiting in other languages.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="db360-365">İşleç Önceliği</span><span class="sxs-lookup"><span data-stu-id="db360-365">Operator Precedence</span></span>

<span data-ttu-id="db360-366">Tüm ikili işleçler, hariç olmak üzere `^`, doğru ilişkilendirilebilir.</span><span class="sxs-lookup"><span data-stu-id="db360-366">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="db360-367">`[` Parantez ve dizi Dilimleme ve dizin oluşturma için herhangi bir işleçten önce `]`bağlayın.</span><span class="sxs-lookup"><span data-stu-id="db360-367">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="db360-368">`Adjoint` Ve diğer tüm işleçlerden önce, dizi dizinlemesi ve `Controlled` sonra bağlama.</span><span class="sxs-lookup"><span data-stu-id="db360-368">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="db360-369">İşlem ve işlev çağırma parantezleri aynı zamanda herhangi bir işleçten önce, ancak dizi dizinlemesi ve komik bir şekilde bağlanır.</span><span class="sxs-lookup"><span data-stu-id="db360-369">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="db360-370">En yüksekten en düşüğe göre öncelik sırasına göre işleçler:</span><span class="sxs-lookup"><span data-stu-id="db360-370">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="db360-371">İşleç</span><span class="sxs-lookup"><span data-stu-id="db360-371">Operator</span></span> | <span data-ttu-id="db360-372">Sayısına</span><span class="sxs-lookup"><span data-stu-id="db360-372">Arity</span></span> | <span data-ttu-id="db360-373">Açıklama</span><span class="sxs-lookup"><span data-stu-id="db360-373">Description</span></span> | <span data-ttu-id="db360-374">İşlenen türleri</span><span class="sxs-lookup"><span data-stu-id="db360-374">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="db360-375">arkasında`!`</span><span class="sxs-lookup"><span data-stu-id="db360-375">trailing `!`</span></span> | <span data-ttu-id="db360-376">Li</span><span class="sxs-lookup"><span data-stu-id="db360-376">Unary</span></span> | <span data-ttu-id="db360-377">Unwrap</span><span class="sxs-lookup"><span data-stu-id="db360-377">Unwrap</span></span> | <span data-ttu-id="db360-378">Kullanıcı tanımlı herhangi bir tür</span><span class="sxs-lookup"><span data-stu-id="db360-378">Any user-defined type</span></span>
 <span data-ttu-id="db360-379">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="db360-379">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="db360-380">Li</span><span class="sxs-lookup"><span data-stu-id="db360-380">Unary</span></span> | <span data-ttu-id="db360-381">Sayısal negatif, bit düzeyinde tamamlama, mantıksal değilleme</span><span class="sxs-lookup"><span data-stu-id="db360-381">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="db360-382">`Int`, `BigInt` için `Double` veya `-`için `Int` veya `BigInt` `~~~`için `Bool``not`</span><span class="sxs-lookup"><span data-stu-id="db360-382">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="db360-383">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-383">Binary</span></span> | <span data-ttu-id="db360-384">Tamsayı güç</span><span class="sxs-lookup"><span data-stu-id="db360-384">Integer power</span></span> | <span data-ttu-id="db360-385">`Int`üs `BigInt` için veya taban `Int` için</span><span class="sxs-lookup"><span data-stu-id="db360-385">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="db360-386">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="db360-386">`/`, `*`, `%`</span></span> | <span data-ttu-id="db360-387">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-387">Binary</span></span> | <span data-ttu-id="db360-388">Bölme, çarpma, tamsayı mod</span><span class="sxs-lookup"><span data-stu-id="db360-388">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="db360-389">`Int`, `BigInt` veya `Double` `/` `Int` için veya `BigInt` için `*``%`</span><span class="sxs-lookup"><span data-stu-id="db360-389">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="db360-390">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="db360-390">`+`, `-`</span></span> | <span data-ttu-id="db360-391">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-391">Binary</span></span> | <span data-ttu-id="db360-392">Ekleme veya dize ve dizi birleştirme, çıkarma</span><span class="sxs-lookup"><span data-stu-id="db360-392">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="db360-393">`Int``BigInt` `Double`veya `String` için bir dizi türü veya`+`</span><span class="sxs-lookup"><span data-stu-id="db360-393">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="db360-394">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="db360-394">`<<<`, `>>>`</span></span> | <span data-ttu-id="db360-395">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-395">Binary</span></span> | <span data-ttu-id="db360-396">Sol SHIFT, sağa kaydırma</span><span class="sxs-lookup"><span data-stu-id="db360-396">Left shift, right shift</span></span> | <span data-ttu-id="db360-397">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="db360-397">`Int` or `BigInt`</span></span>
 <span data-ttu-id="db360-398">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="db360-398">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="db360-399">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-399">Binary</span></span> | <span data-ttu-id="db360-400">Küçüktür, küçüktür veya eşittir, büyüktür, büyüktür veya eşittir karşılaştırmaları</span><span class="sxs-lookup"><span data-stu-id="db360-400">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="db360-401">`Int``BigInt` veya`Double`</span><span class="sxs-lookup"><span data-stu-id="db360-401">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="db360-402">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="db360-402">`==`, `!=`</span></span> | <span data-ttu-id="db360-403">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-403">Binary</span></span> | <span data-ttu-id="db360-404">eşit, eşit olmayan karşılaştırmalar</span><span class="sxs-lookup"><span data-stu-id="db360-404">equal, not-equal comparisons</span></span> | <span data-ttu-id="db360-405">herhangi bir ilkel tür</span><span class="sxs-lookup"><span data-stu-id="db360-405">any primitive type</span></span>
 `&&&` | <span data-ttu-id="db360-406">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-406">Binary</span></span> | <span data-ttu-id="db360-407">Bit düzeyinde AND</span><span class="sxs-lookup"><span data-stu-id="db360-407">Bitwise AND</span></span> | <span data-ttu-id="db360-408">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="db360-408">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="db360-409">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-409">Binary</span></span> | <span data-ttu-id="db360-410">Bit düzeyinde XOR</span><span class="sxs-lookup"><span data-stu-id="db360-410">Bitwise XOR</span></span> | <span data-ttu-id="db360-411">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="db360-411">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="db360-412">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-412">Binary</span></span> | <span data-ttu-id="db360-413">Bit düzeyinde OR</span><span class="sxs-lookup"><span data-stu-id="db360-413">Bitwise OR</span></span> | <span data-ttu-id="db360-414">`Int` veya `BigInt`</span><span class="sxs-lookup"><span data-stu-id="db360-414">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="db360-415">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-415">Binary</span></span> | <span data-ttu-id="db360-416">Mantıksal VE</span><span class="sxs-lookup"><span data-stu-id="db360-416">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="db360-417">İkili</span><span class="sxs-lookup"><span data-stu-id="db360-417">Binary</span></span> | <span data-ttu-id="db360-418">Mantıksal VEYA</span><span class="sxs-lookup"><span data-stu-id="db360-418">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="db360-419">İkili/üçlü</span><span class="sxs-lookup"><span data-stu-id="db360-419">Binary/Ternary</span></span> | <span data-ttu-id="db360-420">Range işleci</span><span class="sxs-lookup"><span data-stu-id="db360-420">Range operator</span></span> | `Int`
 <span data-ttu-id="db360-421">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="db360-421">`?` `|`</span></span> | <span data-ttu-id="db360-422">Üçlü</span><span class="sxs-lookup"><span data-stu-id="db360-422">Ternary</span></span> | <span data-ttu-id="db360-423">Koşullu</span><span class="sxs-lookup"><span data-stu-id="db360-423">Conditional</span></span> | <span data-ttu-id="db360-424">`Bool`Sol taraftaki</span><span class="sxs-lookup"><span data-stu-id="db360-424">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="db360-425">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="db360-425">`w/` `<-`</span></span> | <span data-ttu-id="db360-426">Üçlü</span><span class="sxs-lookup"><span data-stu-id="db360-426">Ternary</span></span> | <span data-ttu-id="db360-427">Kopyala ve Güncelleştir</span><span class="sxs-lookup"><span data-stu-id="db360-427">Copy-and-update</span></span> | <span data-ttu-id="db360-428">bkz. [kopyalama ve güncelleştirme ifadeleri](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="db360-428">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>
