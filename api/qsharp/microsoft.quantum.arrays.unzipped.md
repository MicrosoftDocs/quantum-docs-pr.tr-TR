---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Sıkıştırılmış olmayan işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845376"
---
# <a name="unzipped-function"></a><span data-ttu-id="e050f-102">Sıkıştırılmış olmayan işlev</span><span class="sxs-lookup"><span data-stu-id="e050f-102">Unzipped function</span></span>

<span data-ttu-id="e050f-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e050f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e050f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e050f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e050f-105">2 tanımlama grubu dizisi verildiğinde, her biri giriş dizisinin tanımlama gruplarının öğelerini içeren iki dizinin bir kümesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e050f-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="e050f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e050f-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="e050f-107">ARR: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="e050f-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="e050f-108">2 tanımlama grubu içeren bir dizi</span><span class="sxs-lookup"><span data-stu-id="e050f-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="e050f-109">Çıkış: ('T [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="e050f-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="e050f-110">İlk biri giriş tanımlama gruplarının tüm ilk öğelerini içeren, ikinci diğeri giriş tanımlama gruplarının tüm ikinci öğelerini içeren iki dizi.</span><span class="sxs-lookup"><span data-stu-id="e050f-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e050f-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e050f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e050f-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e050f-112">'T</span></span>

<span data-ttu-id="e050f-113">Her bir tanımlama alanındaki ilk öğenin türü</span><span class="sxs-lookup"><span data-stu-id="e050f-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="e050f-114">' U</span><span class="sxs-lookup"><span data-stu-id="e050f-114">'U</span></span>

<span data-ttu-id="e050f-115">Her bir tanımlama alanındaki ikinci öğe türü</span><span class="sxs-lookup"><span data-stu-id="e050f-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="e050f-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="e050f-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="e050f-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e050f-117">See Also</span></span>

- [<span data-ttu-id="e050f-118">Microsoft.Quantum.Arrays.Zipuygulanmış</span><span class="sxs-lookup"><span data-stu-id="e050f-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)