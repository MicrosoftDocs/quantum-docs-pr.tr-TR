---
title: 'Microsoft Q # Numerics kitaplığını kullanma'
description: Microsoft hisse türü kitaplığı 'nda bulunan türler ve işlemler hakkında bilgi edinin.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276116"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="3a691-103">Numerics kitaplığını kullanma</span><span class="sxs-lookup"><span data-stu-id="3a691-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="3a691-104">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="3a691-104">Overview</span></span>

<span data-ttu-id="3a691-105">Numerics kitaplığı üç bileşenden oluşur</span><span class="sxs-lookup"><span data-stu-id="3a691-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="3a691-106">Tamsayı kurban ve Karşılaştırıcılar ile **temel tamsayı aritmetiği**</span><span class="sxs-lookup"><span data-stu-id="3a691-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="3a691-107">Temel işlevlerin üstünde oluşturulan **üst düzey tamsayı işlevselliği** ; çarpma, bölme, Inversion vb. içerir.  işaretli ve işaretsiz tamsayılar için.</span><span class="sxs-lookup"><span data-stu-id="3a691-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="3a691-108">Sabit noktalı başlatma, toplama, çarpma, karşılıklı, polinom değerlendirmesi ve ölçüyle **sabit noktalı aritmetik işlevsellik** .</span><span class="sxs-lookup"><span data-stu-id="3a691-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="3a691-109">Bu bileşenlere tek bir ifade kullanılarak erişilebilir `open` :</span><span class="sxs-lookup"><span data-stu-id="3a691-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="3a691-110">Türler</span><span class="sxs-lookup"><span data-stu-id="3a691-110">Types</span></span>

<span data-ttu-id="3a691-111">Numerics kitaplığı aşağıdaki türleri destekler</span><span class="sxs-lookup"><span data-stu-id="3a691-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="3a691-112">**`LittleEndian`**: `qArr : Qubit[]` En az önemli bir bit belirten bir tamsayıyı temsil eden bir qubit dizisi `qArr[0]` .</span><span class="sxs-lookup"><span data-stu-id="3a691-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="3a691-113">**`SignedLittleEndian`**: `LittleEndian` İki öğesinin tamamlayıcısı içinde depolanan işaretli bir tamsayıyı temsil ettiğinden olduğu gibi.</span><span class="sxs-lookup"><span data-stu-id="3a691-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="3a691-114">**`FixedPoint`**: Bir qubit dizisi ve ikili nokta konumundan oluşan gerçek bir sayıyı temsil eder `qArr2 : Qubit[]` `pos` . Bu, ikili noktanın solundaki ikili basamak sayısını sayar.</span><span class="sxs-lookup"><span data-stu-id="3a691-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="3a691-115">`qArr2`, ile aynı şekilde depolanır `SignedLittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="3a691-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="3a691-116">Operations</span><span class="sxs-lookup"><span data-stu-id="3a691-116">Operations</span></span>

<span data-ttu-id="3a691-117">Yukarıdaki üç türden her biri için çeşitli işlemler mevcuttur:</span><span class="sxs-lookup"><span data-stu-id="3a691-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="3a691-118">Toplama</span><span class="sxs-lookup"><span data-stu-id="3a691-118">Addition</span></span>
    - <span data-ttu-id="3a691-119">Karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="3a691-119">Comparison</span></span>
    - <span data-ttu-id="3a691-120">Çarpma</span><span class="sxs-lookup"><span data-stu-id="3a691-120">Multiplication</span></span>
    - <span data-ttu-id="3a691-121">Karelerini alıp</span><span class="sxs-lookup"><span data-stu-id="3a691-121">Squaring</span></span>
    - <span data-ttu-id="3a691-122">Bölme (geri kalan)</span><span class="sxs-lookup"><span data-stu-id="3a691-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="3a691-123">Toplama</span><span class="sxs-lookup"><span data-stu-id="3a691-123">Addition</span></span>
    - <span data-ttu-id="3a691-124">Karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="3a691-124">Comparison</span></span>
    - <span data-ttu-id="3a691-125">INVERSION modül 2 ' nin tamamlayıcı</span><span class="sxs-lookup"><span data-stu-id="3a691-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="3a691-126">Çarpma</span><span class="sxs-lookup"><span data-stu-id="3a691-126">Multiplication</span></span>
    - <span data-ttu-id="3a691-127">Karelerini alıp</span><span class="sxs-lookup"><span data-stu-id="3a691-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="3a691-128">Klasik değerlere hazırlık/başlatma</span><span class="sxs-lookup"><span data-stu-id="3a691-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="3a691-129">Toplama (klasik sabit veya diğer hisse sabit noktası)</span><span class="sxs-lookup"><span data-stu-id="3a691-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="3a691-130">Karşılaştırma</span><span class="sxs-lookup"><span data-stu-id="3a691-130">Comparison</span></span>
    - <span data-ttu-id="3a691-131">Çarpma</span><span class="sxs-lookup"><span data-stu-id="3a691-131">Multiplication</span></span>
    - <span data-ttu-id="3a691-132">Karelerini alıp</span><span class="sxs-lookup"><span data-stu-id="3a691-132">Squaring</span></span>
    - <span data-ttu-id="3a691-133">Çift ve tek işlevler için özelleşmede polinom değerlendirmesi</span><span class="sxs-lookup"><span data-stu-id="3a691-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="3a691-134">Karşılıklı (1/x)</span><span class="sxs-lookup"><span data-stu-id="3a691-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="3a691-135">Ölçüm (Klasik Çift)</span><span class="sxs-lookup"><span data-stu-id="3a691-135">Measurement (classical Double)</span></span>

<span data-ttu-id="3a691-136">Bu işlemlerin her biri için daha fazla bilgi ve ayrıntılı belgeler için [docs.Microsoft.com](https://docs.microsoft.com/quantum) adresindeki Q # kitaplığı başvuru belgelerine bakın.</span><span class="sxs-lookup"><span data-stu-id="3a691-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="3a691-137">Örnek: tamsayı ekleme</span><span class="sxs-lookup"><span data-stu-id="3a691-137">Sample: Integer addition</span></span>

<span data-ttu-id="3a691-138">Temel bir örnek olarak, $ $ \ ayraç x\tusi\mapsto \tusx\ket {x + y} $ $ işlemini, yani n-qubit Integer $x $ ve n-veya (n + 1)-qubit, $ (x + y) $ toplamına eşlendiği bir giriş olarak $y $ olduğunu bir işlem.</span><span class="sxs-lookup"><span data-stu-id="3a691-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="3a691-139">$Y $ bir $n $-bit kasada depolanıyorsa, Sum 'un hesaplanmış mod $2 ^ n $ olduğunu unutmayın.</span><span class="sxs-lookup"><span data-stu-id="3a691-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="3a691-140">Bu işlem, hisse geliştirme setini kullanarak aşağıdaki gibi uygulanabilir:</span><span class="sxs-lookup"><span data-stu-id="3a691-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="3a691-141">Örnek: Düzgünleştir işlevlerini değerlendirme</span><span class="sxs-lookup"><span data-stu-id="3a691-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="3a691-142">$ \Sin (x) $ gibi kesintisiz işlevleri bir hisse bilgisayarında değerlendirmek için, $x $ 'nin hisse numarası olduğu, `FixedPoint` hisse geliştirme seti Numerics kitaplığı, işlemleri `EvaluatePolynomialFxP` ve sunar `Evaluate[Even/Odd]PolynomialFxP` .</span><span class="sxs-lookup"><span data-stu-id="3a691-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="3a691-143">Birincisi, `EvaluatePolynomialFxP` , $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cnoktalar + a_dx ^ d, $ $ ($d $ *derecesini*gösterir) biçiminde bir polinom değerini değerlendirebilmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="3a691-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="3a691-144">Bunu yapmak için, gerekli olan polinom katsayıları `[a_0,..., a_d]` (türü `Double[]` ), giriş `x : FixedPoint` ve çıkış `y : FixedPoint` (başlangıçta sıfır):</span><span class="sxs-lookup"><span data-stu-id="3a691-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="3a691-145">Sonuç, $P (x) = 1 + 2x $, içinde depolanacak `yFxP` .</span><span class="sxs-lookup"><span data-stu-id="3a691-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="3a691-146">İkinci, `EvaluateEvenPolynomialFxP` ve üçüncü, `EvaluateOddPolynomialFxP` sırasıyla, hatta ve tek işlevler için özelleştirilmiş çalışmalardır.</span><span class="sxs-lookup"><span data-stu-id="3a691-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="3a691-147">Diğer bir deyişle, Çift/tek işlevi için $f (x) $ ve $ $ P_ {çift} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cnoktalar + a_d x ^ {2D}, $ $ $f (x) $, sırasıyla $P _ {çift} (x) $ veya $P _ {tek} (x): = x\cdot P_ {çift} (x) $.</span><span class="sxs-lookup"><span data-stu-id="3a691-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="3a691-148">Q # içinde, bu iki durum şu şekilde işlenebilir:</span><span class="sxs-lookup"><span data-stu-id="3a691-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="3a691-149">$P _ {çift} (x) = 1 + 2x ^ 2 $ olduğunu değerlendirir ve</span><span class="sxs-lookup"><span data-stu-id="3a691-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="3a691-150">$P _ {tek} (x) = x + 2x ^ 3 $ öğesini değerlendirir.</span><span class="sxs-lookup"><span data-stu-id="3a691-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="3a691-151">Daha fazla örnek</span><span class="sxs-lookup"><span data-stu-id="3a691-151">More samples</span></span>

<span data-ttu-id="3a691-152">[Ana örnekler deposunda](https://github.com/Microsoft/Quantum)daha fazla örnek bulabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="3a691-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="3a691-153">Başlamak için depoyu kopyalayın ve `Numerics` alt klasörü açın:</span><span class="sxs-lookup"><span data-stu-id="3a691-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="3a691-154">Ardından, `cd` örnek klasörlerden birine ve örneği ile çalıştırın</span><span class="sxs-lookup"><span data-stu-id="3a691-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
