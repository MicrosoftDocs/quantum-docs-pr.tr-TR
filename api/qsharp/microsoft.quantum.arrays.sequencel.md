---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730023"
---
# <a name="sequencel-function"></a><span data-ttu-id="614ab-102">SequenceL işlevi</span><span class="sxs-lookup"><span data-stu-id="614ab-102">SequenceL function</span></span>

<span data-ttu-id="614ab-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="614ab-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="614ab-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="614ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="614ab-105">Verilen bir aralıktaki tamsayıların dizisini alır.</span><span class="sxs-lookup"><span data-stu-id="614ab-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="614ab-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="614ab-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="614ab-107">Kimden: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="614ab-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="614ab-108">Aralığın kapsamlı başlangıç dizini.</span><span class="sxs-lookup"><span data-stu-id="614ab-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="614ab-109">Şu şekilde: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="614ab-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="614ab-110">Aralıktan küçük olmayan aralığın kapsamlı bir bitiş dizini `from` .</span><span class="sxs-lookup"><span data-stu-id="614ab-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="614ab-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="614ab-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="614ab-112">Sayı dizisini içeren bir dizi `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="614ab-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="614ab-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="614ab-113">Remarks</span></span>

<span data-ttu-id="614ab-114">Ve arasındaki fark `from` `to` bir değere sığması gerekir `Int` .</span><span class="sxs-lookup"><span data-stu-id="614ab-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>