---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: c898178b6385b27f753509f0748a8b666b5066bd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220085"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="a8ad6-102">TupleArrayAsNestedArray işlevi</span><span class="sxs-lookup"><span data-stu-id="a8ad6-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="a8ad6-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a8ad6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a8ad6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8ad6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8ad6-105">2 başlıkların listesini iç içe geçmiş bir diziye dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="a8ad6-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="a8ad6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a8ad6-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="a8ad6-107">tupleList: ('T, 'T) []</span><span class="sxs-lookup"><span data-stu-id="a8ad6-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="a8ad6-108">İç içe bir dizide kapatılacak 2 tanımlama gruplarının listesi.</span><span class="sxs-lookup"><span data-stu-id="a8ad6-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="a8ad6-109">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="a8ad6-109">Output : 'T[][]</span></span>

<span data-ttu-id="a8ad6-110">TupleList ile eşleşen ve uzunluğu olan iç içe bir dizi.</span><span class="sxs-lookup"><span data-stu-id="a8ad6-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="a8ad6-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="a8ad6-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="a8ad6-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a8ad6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8ad6-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="a8ad6-113">'T</span></span>

