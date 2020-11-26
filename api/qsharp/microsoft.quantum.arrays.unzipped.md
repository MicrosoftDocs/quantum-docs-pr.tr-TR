---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Sıkıştırılmış olmayan işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219966"
---
# <a name="unzipped-function"></a><span data-ttu-id="4e987-102">Sıkıştırılmış olmayan işlev</span><span class="sxs-lookup"><span data-stu-id="4e987-102">Unzipped function</span></span>

<span data-ttu-id="4e987-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4e987-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4e987-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e987-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e987-105">2 tanımlama grubu dizisi verildiğinde, her biri giriş dizisinin tanımlama gruplarının öğelerini içeren iki dizinin bir kümesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="4e987-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="4e987-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4e987-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="4e987-107">ARR: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="4e987-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="4e987-108">2 tanımlama grubu içeren bir dizi</span><span class="sxs-lookup"><span data-stu-id="4e987-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="4e987-109">Çıkış: ('T [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="4e987-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="4e987-110">İlk biri giriş tanımlama gruplarının tüm ilk öğelerini içeren, ikinci diğeri giriş tanımlama gruplarının tüm ikinci öğelerini içeren iki dizi.</span><span class="sxs-lookup"><span data-stu-id="4e987-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4e987-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4e987-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e987-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4e987-112">'T</span></span>

<span data-ttu-id="4e987-113">Her bir tanımlama alanındaki ilk öğenin türü</span><span class="sxs-lookup"><span data-stu-id="4e987-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="4e987-114">' U</span><span class="sxs-lookup"><span data-stu-id="4e987-114">'U</span></span>

<span data-ttu-id="4e987-115">Her bir tanımlama alanındaki ikinci öğe türü</span><span class="sxs-lookup"><span data-stu-id="4e987-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="4e987-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4e987-116">See Also</span></span>

- [<span data-ttu-id="4e987-117">Microsoft.Quantum.Arrays.Zipuygulanmış</span><span class="sxs-lookup"><span data-stu-id="4e987-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)