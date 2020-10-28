---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Issıralanmış işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: 330c1f789585f64cf255bc74f8a9c1ccf81b009e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730170"
---
# <a name="issorted-function"></a><span data-ttu-id="0b63f-102">Issıralanmış işlevi</span><span class="sxs-lookup"><span data-stu-id="0b63f-102">IsSorted function</span></span>

<span data-ttu-id="0b63f-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0b63f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0b63f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b63f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b63f-105">Dizi verildiğinde, bu dizinin belirli bir karşılaştırma işlevi tarafından tanımlandığı şekilde sıralanıp sıralanmadığını döndürür.</span><span class="sxs-lookup"><span data-stu-id="0b63f-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="0b63f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0b63f-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="0b63f-107">Karşılaştırma: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0b63f-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0b63f-108">İki öğeyi karşılaştıran bir işlev `a` , daha küçük veya eşittir olarak kabul edilir `b` `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="0b63f-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="0b63f-109">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="0b63f-109">array : 'T[]</span></span>

<span data-ttu-id="0b63f-110">Denetlenecek dizi.</span><span class="sxs-lookup"><span data-stu-id="0b63f-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0b63f-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0b63f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0b63f-112">`true` ve yalnızca her öğe çifti için `a` ve `b` `array` Bu sırada oluşumda varsa, `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="0b63f-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b63f-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="0b63f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b63f-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="0b63f-114">'T</span></span>

<span data-ttu-id="0b63f-115">Her öğesinin türü `array` .</span><span class="sxs-lookup"><span data-stu-id="0b63f-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b63f-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0b63f-116">Remarks</span></span>

<span data-ttu-id="0b63f-117">İşlevin `comparison` geçişli olduğu varsayılır, `comparison(a, b)` ve `comparison(b, c)` daha sonra `comparison(a, c)` varsayılır.</span><span class="sxs-lookup"><span data-stu-id="0b63f-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="0b63f-118">Bu özellik tutmadıysanız, bu işlevin çıktısı yanlış olabilir.</span><span class="sxs-lookup"><span data-stu-id="0b63f-118">If this property does not hold, then the output of this function may be incorrect.</span></span>