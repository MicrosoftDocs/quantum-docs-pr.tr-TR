---
uid: Microsoft.Quantum.Arrays.Swapped
title: Takas edilen işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850945"
---
# <a name="swapped-function"></a><span data-ttu-id="5c684-102">Takas edilen işlev</span><span class="sxs-lookup"><span data-stu-id="5c684-102">Swapped function</span></span>

<span data-ttu-id="5c684-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5c684-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5c684-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c684-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c684-105">Bir dizide iki öğenin takas düzeyini uygular.</span><span class="sxs-lookup"><span data-stu-id="5c684-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5c684-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5c684-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="5c684-107">Firstındex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c684-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c684-108">Takas edilecek ilk öğenin dizini.</span><span class="sxs-lookup"><span data-stu-id="5c684-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="5c684-109">Ikincdizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c684-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c684-110">Takas edilecek ikinci öğenin dizini.</span><span class="sxs-lookup"><span data-stu-id="5c684-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="5c684-111">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="5c684-111">arr : 'T[]</span></span>

<span data-ttu-id="5c684-112">Takas edilecek öğeler içeren dizi.</span><span class="sxs-lookup"><span data-stu-id="5c684-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="5c684-113">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="5c684-113">Output : 'T[]</span></span>

<span data-ttu-id="5c684-114">Yerinde değiştirme uygulanmış dizi.</span><span class="sxs-lookup"><span data-stu-id="5c684-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="5c684-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="5c684-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="5c684-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5c684-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5c684-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="5c684-117">'T</span></span>

