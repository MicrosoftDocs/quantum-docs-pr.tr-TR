---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845386"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="5989a-102">TupleArrayAsNestedArray işlevi</span><span class="sxs-lookup"><span data-stu-id="5989a-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="5989a-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5989a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5989a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5989a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5989a-105">2 başlıkların listesini iç içe geçmiş bir diziye dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="5989a-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="5989a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5989a-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="5989a-107">tupleList: ('T, 'T) []</span><span class="sxs-lookup"><span data-stu-id="5989a-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="5989a-108">İç içe bir dizide kapatılacak 2 tanımlama gruplarının listesi.</span><span class="sxs-lookup"><span data-stu-id="5989a-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="5989a-109">Çıkış: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="5989a-109">Output : 'T[][]</span></span>

<span data-ttu-id="5989a-110">TupleList ile eşleşen ve uzunluğu olan iç içe bir dizi.</span><span class="sxs-lookup"><span data-stu-id="5989a-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="5989a-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="5989a-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="5989a-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5989a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5989a-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="5989a-113">'T</span></span>

