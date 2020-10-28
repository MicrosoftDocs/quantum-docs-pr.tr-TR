---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 917f35db949790ab3ae6e7a2184bcfcf5ed50be6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729975"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="5916d-102">TupleArrayAsNestedArray işlevi</span><span class="sxs-lookup"><span data-stu-id="5916d-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="5916d-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5916d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5916d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5916d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5916d-105">2 başlıkların listesini iç içe geçmiş bir diziye dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="5916d-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="5916d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5916d-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="5916d-107">tupleList: ('T, 'T) []</span><span class="sxs-lookup"><span data-stu-id="5916d-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="5916d-108">İç içe bir dizide kapatılacak 2 tanımlama gruplarının listesi.</span><span class="sxs-lookup"><span data-stu-id="5916d-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="5916d-109">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="5916d-109">Output : 'T[][]</span></span>

<span data-ttu-id="5916d-110">TupleList ile eşleşen ve uzunluğu olan iç içe bir dizi.</span><span class="sxs-lookup"><span data-stu-id="5916d-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="5916d-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="5916d-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="5916d-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5916d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5916d-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="5916d-113">'T</span></span>

