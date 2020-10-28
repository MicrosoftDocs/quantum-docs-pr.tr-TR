---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730034"
---
# <a name="sequencei-function"></a><span data-ttu-id="2a33f-102">SequenceI işlevi</span><span class="sxs-lookup"><span data-stu-id="2a33f-102">SequenceI function</span></span>

<span data-ttu-id="2a33f-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2a33f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2a33f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a33f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a33f-105">Verilen bir aralıktaki tamsayıların dizisini alır.</span><span class="sxs-lookup"><span data-stu-id="2a33f-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="2a33f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2a33f-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="2a33f-107">Kimden: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a33f-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a33f-108">Aralığın kapsamlı başlangıç dizini.</span><span class="sxs-lookup"><span data-stu-id="2a33f-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="2a33f-109">to: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2a33f-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2a33f-110">Aralıktan küçük olmayan aralığın kapsamlı bir bitiş dizini `from` .</span><span class="sxs-lookup"><span data-stu-id="2a33f-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="2a33f-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2a33f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2a33f-112">Sayı dizisini içeren bir dizi `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="2a33f-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>