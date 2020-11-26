---
uid: Microsoft.Quantum.Arrays.Padded
title: Doldurulmuş işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220544"
---
# <a name="padded-function"></a><span data-ttu-id="f9166-102">Doldurulmuş işlev</span><span class="sxs-lookup"><span data-stu-id="f9166-102">Padded function</span></span>

<span data-ttu-id="f9166-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f9166-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f9166-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9166-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9166-105">Belirtilen bir uzunluğa kadar belirtilen değerlerle doldurulmuş bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="f9166-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f9166-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f9166-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="f9166-107">nElementsTotal: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f9166-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f9166-108">Doldurulmuş dizinin uzunluğu.</span><span class="sxs-lookup"><span data-stu-id="f9166-108">The length of the padded array.</span></span> <span data-ttu-id="f9166-109">Bu pozitif ise, `inputArray` baş tarafında doldurulur.</span><span class="sxs-lookup"><span data-stu-id="f9166-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="f9166-110">Bu negatifse, `inputArray` kuyruklu doldurulur.</span><span class="sxs-lookup"><span data-stu-id="f9166-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="f9166-111">defaultElement: 'T</span><span class="sxs-lookup"><span data-stu-id="f9166-111">defaultElement : 'T</span></span>

<span data-ttu-id="f9166-112">Doldurma öğeleri için kullanılacak varsayılan değer.</span><span class="sxs-lookup"><span data-stu-id="f9166-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="f9166-113">ınputarray: 'T []</span><span class="sxs-lookup"><span data-stu-id="f9166-113">inputArray : 'T[]</span></span>

<span data-ttu-id="f9166-114">Değerleri çıktı dizisinin başındaki dizi.</span><span class="sxs-lookup"><span data-stu-id="f9166-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="f9166-115">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="f9166-115">Output : 'T[]</span></span>

<span data-ttu-id="f9166-116">En fazla `output` `inputArray` `defaultElement` uzunluğu olan s ile `output` başlayan bir dizi `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="f9166-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f9166-117">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f9166-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9166-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f9166-118">'T</span></span>

<span data-ttu-id="f9166-119">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="f9166-119">The type of the array elements.</span></span>