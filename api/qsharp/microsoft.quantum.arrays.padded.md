---
uid: Microsoft.Quantum.Arrays.Padded
title: Doldurulmuş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845558"
---
# <a name="padded-function"></a><span data-ttu-id="28aa3-102">Doldurulmuş işlev</span><span class="sxs-lookup"><span data-stu-id="28aa3-102">Padded function</span></span>

<span data-ttu-id="28aa3-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="28aa3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="28aa3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28aa3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28aa3-105">Belirtilen bir uzunluğa kadar belirtilen değerlerle doldurulmuş bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="28aa3-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="28aa3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="28aa3-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="28aa3-107">nElementsTotal: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28aa3-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28aa3-108">Doldurulmuş dizinin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="28aa3-108">The length of the padded array.</span></span> <span data-ttu-id="28aa3-109">Bu pozitif ise, `inputArray` baş tarafında doldurulur.</span><span class="sxs-lookup"><span data-stu-id="28aa3-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="28aa3-110">Bu negatifse, `inputArray` kuyruklu doldurulur.</span><span class="sxs-lookup"><span data-stu-id="28aa3-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="28aa3-111">defaultElement: 'T</span><span class="sxs-lookup"><span data-stu-id="28aa3-111">defaultElement : 'T</span></span>

<span data-ttu-id="28aa3-112">Doldurma öğeleri için kullanılacak varsayılan değer.</span><span class="sxs-lookup"><span data-stu-id="28aa3-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="28aa3-113">ınputarray: 'T []</span><span class="sxs-lookup"><span data-stu-id="28aa3-113">inputArray : 'T[]</span></span>

<span data-ttu-id="28aa3-114">Değerleri çıktı dizisinin başındaki dizi.</span><span class="sxs-lookup"><span data-stu-id="28aa3-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="28aa3-115">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="28aa3-115">Output : 'T[]</span></span>

<span data-ttu-id="28aa3-116">En fazla `output` `inputArray` `defaultElement` uzunluğu olan s ile `output` başlayan bir dizi `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="28aa3-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="28aa3-117">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="28aa3-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28aa3-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="28aa3-118">'T</span></span>

<span data-ttu-id="28aa3-119">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="28aa3-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="28aa3-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="28aa3-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```