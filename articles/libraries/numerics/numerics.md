---
title: Numerics kitaplığını kullanma | Microsoft Docs
description: Numerics kitaplığını kullanma
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: ca24ff60cd9ae5077c7f4bae0012fe1180d7e6d4
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821040"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="f8195-103">Numerics kitaplığını kullanma</span><span class="sxs-lookup"><span data-stu-id="f8195-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="f8195-104">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="f8195-104">Overview</span></span>

<span data-ttu-id="f8195-105">Numerics kitaplığı üç bileşenden oluşur</span><span class="sxs-lookup"><span data-stu-id="f8195-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="f8195-106">Tamsayı kurban ve Karşılaştırıcılar ile **temel tamsayı aritmetiği**</span><span class="sxs-lookup"><span data-stu-id="f8195-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="f8195-107">Temel işlevlerin üstünde oluşturulan **üst düzey tamsayı işlevselliği** ; çarpma, bölme, Inversion vb. içerir.  işaretli ve işaretsiz tamsayılar için.</span><span class="sxs-lookup"><span data-stu-id="f8195-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="f8195-108">Sabit noktalı başlatma, toplama, çarpma, karşılıklı, polinom değerlendirmesi ve ölçüyle **sabit noktalı aritmetik işlevsellik** .</span><span class="sxs-lookup"><span data-stu-id="f8195-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="f8195-109">Bu bileşenlere, tek bir `open` ekstresi kullanılarak erişilebilir:</span><span class="sxs-lookup"><span data-stu-id="f8195-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="f8195-110">Türler</span><span class="sxs-lookup"><span data-stu-id="f8195-110">Types</span></span>

<span data-ttu-id="f8195-111">Numerics kitaplığı aşağıdaki türleri destekler</span><span class="sxs-lookup"><span data-stu-id="f8195-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="f8195-112">**`LittleEndian`** : `qArr[0]` en az önemli biti gösterdiği bir tamsayıyı temsil eden bir qubit dizisi `qArr : Qubit[]`.</span><span class="sxs-lookup"><span data-stu-id="f8195-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="f8195-113">**`SignedLittleEndian`** : iki öğenin tamamlayıcısı içinde depolanan işaretli bir tamsayıyı temsil ettiğinden, `LittleEndian` aynı.</span><span class="sxs-lookup"><span data-stu-id="f8195-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="f8195-114">**`FixedPoint`** : bir qubit dizi `qArr2 : Qubit[]` ve ikili nokta `pos`konumundan oluşan gerçek bir sayıyı temsil eder. Bu, ikili noktanın solundaki ikili basamak sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="f8195-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="f8195-115">`qArr2`, `SignedLittleEndian`ile aynı şekilde depolanır.</span><span class="sxs-lookup"><span data-stu-id="f8195-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="f8195-116">Operations</span><span class="sxs-lookup"><span data-stu-id="f8195-116">Operations</span></span>

<span data-ttu-id="f8195-117">Yukarıdaki üç türden her biri için çeşitli işlemler mevcuttur:</span><span class="sxs-lookup"><span data-stu-id="f8195-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="f8195-118">Ek olarak</span><span class="sxs-lookup"><span data-stu-id="f8195-118">Addition</span></span>
    - <span data-ttu-id="f8195-119">Karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="f8195-119">Comparison</span></span>
    - <span data-ttu-id="f8195-120">Anda</span><span class="sxs-lookup"><span data-stu-id="f8195-120">Multiplication</span></span>
    - <span data-ttu-id="f8195-121">Karelerini alıp</span><span class="sxs-lookup"><span data-stu-id="f8195-121">Squaring</span></span>
    - <span data-ttu-id="f8195-122">Bölme (geri kalan)</span><span class="sxs-lookup"><span data-stu-id="f8195-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="f8195-123">Ek olarak</span><span class="sxs-lookup"><span data-stu-id="f8195-123">Addition</span></span>
    - <span data-ttu-id="f8195-124">Karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="f8195-124">Comparison</span></span>
    - <span data-ttu-id="f8195-125">INVERSION modül 2 ' nin tamamlayıcı</span><span class="sxs-lookup"><span data-stu-id="f8195-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="f8195-126">Anda</span><span class="sxs-lookup"><span data-stu-id="f8195-126">Multiplication</span></span>
    - <span data-ttu-id="f8195-127">Karelerini alıp</span><span class="sxs-lookup"><span data-stu-id="f8195-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="f8195-128">Klasik değerlere hazırlık/başlatma</span><span class="sxs-lookup"><span data-stu-id="f8195-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="f8195-129">Toplama (klasik sabit veya diğer hisse sabit noktası)</span><span class="sxs-lookup"><span data-stu-id="f8195-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="f8195-130">Karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="f8195-130">Comparison</span></span>
    - <span data-ttu-id="f8195-131">Anda</span><span class="sxs-lookup"><span data-stu-id="f8195-131">Multiplication</span></span>
    - <span data-ttu-id="f8195-132">Karelerini alıp</span><span class="sxs-lookup"><span data-stu-id="f8195-132">Squaring</span></span>
    - <span data-ttu-id="f8195-133">Çift ve tek işlevler için özelleşmede polinom değerlendirmesi</span><span class="sxs-lookup"><span data-stu-id="f8195-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="f8195-134">Karşılıklı (1/x)</span><span class="sxs-lookup"><span data-stu-id="f8195-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="f8195-135">Ölçüm (Klasik Çift)</span><span class="sxs-lookup"><span data-stu-id="f8195-135">Measurement (classical Double)</span></span>

<span data-ttu-id="f8195-136">Bu işlemlerin her biri için daha fazla bilgi ve ayrıntılı belgeler için [docs.Microsoft.com](https://docs.microsoft.com/quantum) adresindeki Q # kitaplığı başvuru belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="f8195-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="f8195-137">Örnek: tamsayı ekleme</span><span class="sxs-lookup"><span data-stu-id="f8195-137">Sample: Integer addition</span></span>

<span data-ttu-id="f8195-138">Temel bir örnek olarak, $ $ \ ayraç x\tusi\mapsto \tusx\ket {x + y} $ $ işlemini, yani n-qubit Integer $x $ ve n-veya (n + 1)-qubit, $ (x + y) $ toplamına eşlendiği bir giriş olarak $y $ olduğunu bir işlem.</span><span class="sxs-lookup"><span data-stu-id="f8195-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="f8195-139">$Y $ bir $n $-bit kasada depolanıyorsa, Sum 'un hesaplanmış mod $2 ^ n $ olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="f8195-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="f8195-140">Bu işlem, hisse geliştirme setini kullanarak aşağıdaki gibi uygulanabilir:</span><span class="sxs-lookup"><span data-stu-id="f8195-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="f8195-141">Örnek: Düzgünleştir işlevlerini değerlendirme</span><span class="sxs-lookup"><span data-stu-id="f8195-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="f8195-142">$ \Sin (x) $ gibi kesintisiz işlevleri bir hisse bilgisayarında değerlendirmek için, $x $ 'nin hisse `FixedPoint` numarası olduğu, hisse geliştirme seti Numerics kitaplığı, işlemler `EvaluatePolynomialFxP` ve `Evaluate[Even/Odd]PolynomialFxP`sağlar.</span><span class="sxs-lookup"><span data-stu-id="f8195-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="f8195-143">Birincisi, `EvaluatePolynomialFxP`, $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cnoktalar + a_dx ^ d, $ $ biçiminde bir polinom değerini değerlendirmenize olanak tanır; burada $d $ *dereceyi*gösterir.</span><span class="sxs-lookup"><span data-stu-id="f8195-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="f8195-144">Bunu yapmak için, gerekli olan polinom katsayıları `[a_0,..., a_d]` (`Double[]`türü), giriş `x : FixedPoint` ve çıkış `y : FixedPoint` (başlangıçta sıfır):</span><span class="sxs-lookup"><span data-stu-id="f8195-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="f8195-145">Sonuç, $P (x) = 1 + 2x $, `yFxP`depolanacak.</span><span class="sxs-lookup"><span data-stu-id="f8195-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="f8195-146">İkinci, `EvaluateEvenPolynomialFxP`ve üçüncü `EvaluateOddPolynomialFxP`, sırasıyla, hatta ve tek işlevler için özelleştirilmiş çalışmalardır.</span><span class="sxs-lookup"><span data-stu-id="f8195-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="f8195-147">Diğer bir deyişle, Çift/tek işlevi için $f (x) $ ve $ $ P_ {çift} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cnoktalar + a_d x ^ {2D}, $ $ $f (x) $, sırasıyla $P _ {çift} (x) $ veya $P _ {tek} (x): = x\cdot P_ {çift} (x) $.</span><span class="sxs-lookup"><span data-stu-id="f8195-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="f8195-148">Q # içinde, bu iki durum şu şekilde işlenebilir:</span><span class="sxs-lookup"><span data-stu-id="f8195-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="f8195-149">$P _ {çift} (x) = 1 + 2x ^ 2 $ olduğunu değerlendirir ve</span><span class="sxs-lookup"><span data-stu-id="f8195-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="f8195-150">$P _ {tek} (x) = x + 2x ^ 3 $ öğesini değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="f8195-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="f8195-151">Daha fazla örnek</span><span class="sxs-lookup"><span data-stu-id="f8195-151">More samples</span></span>

<span data-ttu-id="f8195-152">[Ana örnekler deposunda](https://github.com/Microsoft/Quantum)daha fazla örnek bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f8195-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="f8195-153">Başlamak için depoyu kopyalayın ve `Numerics` alt klasörünü açın:</span><span class="sxs-lookup"><span data-stu-id="f8195-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="f8195-154">Ardından, örnek klasörlerden birine `cd` ve örneği kullanarak çalıştırın</span><span class="sxs-lookup"><span data-stu-id="f8195-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
