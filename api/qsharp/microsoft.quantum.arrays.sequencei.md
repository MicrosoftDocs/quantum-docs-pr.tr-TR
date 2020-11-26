---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220306"
---
# <a name="sequencei-function"></a><span data-ttu-id="2c10b-102">SequenceI işlevi</span><span class="sxs-lookup"><span data-stu-id="2c10b-102">SequenceI function</span></span>

<span data-ttu-id="2c10b-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2c10b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2c10b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2c10b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2c10b-105">Verilen bir aralıktaki tamsayıların dizisini alır.</span><span class="sxs-lookup"><span data-stu-id="2c10b-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="2c10b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2c10b-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="2c10b-107">Kimden: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2c10b-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2c10b-108">Aralığın kapsamlı başlangıç dizini.</span><span class="sxs-lookup"><span data-stu-id="2c10b-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="2c10b-109">to: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2c10b-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2c10b-110">Aralıktan küçük olmayan aralığın kapsamlı bir bitiş dizini `from` .</span><span class="sxs-lookup"><span data-stu-id="2c10b-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="2c10b-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2c10b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2c10b-112">Sayı dizisini içeren bir dizi `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="2c10b-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>