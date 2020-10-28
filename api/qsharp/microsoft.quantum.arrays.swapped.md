---
uid: Microsoft.Quantum.Arrays.Swapped
title: Takas edilen işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729986"
---
# <a name="swapped-function"></a><span data-ttu-id="87f01-102">Takas edilen işlev</span><span class="sxs-lookup"><span data-stu-id="87f01-102">Swapped function</span></span>

<span data-ttu-id="87f01-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="87f01-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="87f01-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87f01-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87f01-105">Bir dizide iki öğenin takas düzeyini uygular.</span><span class="sxs-lookup"><span data-stu-id="87f01-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="87f01-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="87f01-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="87f01-107">Firstındex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87f01-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87f01-108">Takas edilecek ilk öğenin dizini.</span><span class="sxs-lookup"><span data-stu-id="87f01-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="87f01-109">Ikincdizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87f01-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87f01-110">Takas edilecek ikinci öğenin dizini.</span><span class="sxs-lookup"><span data-stu-id="87f01-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="87f01-111">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="87f01-111">arr : 'T[]</span></span>

<span data-ttu-id="87f01-112">Takas edilecek öğeler içeren dizi.</span><span class="sxs-lookup"><span data-stu-id="87f01-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="87f01-113">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="87f01-113">Output : 'T[]</span></span>

<span data-ttu-id="87f01-114">Yerinde değiştirme uygulanmış dizi.</span><span class="sxs-lookup"><span data-stu-id="87f01-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="87f01-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="87f01-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="87f01-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="87f01-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87f01-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="87f01-117">'T</span></span>

