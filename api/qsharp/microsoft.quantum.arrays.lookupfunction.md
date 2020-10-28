---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730151"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="3b4bc-102">LookupFunction işlevi</span><span class="sxs-lookup"><span data-stu-id="3b4bc-102">LookupFunction function</span></span>

<span data-ttu-id="3b4bc-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3b4bc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3b4bc-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b4bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b4bc-105">Dizi verildiğinde, bu dizinin öğelerini döndüren bir işlev döndürür.</span><span class="sxs-lookup"><span data-stu-id="3b4bc-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="3b4bc-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="3b4bc-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="3b4bc-107">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="3b4bc-107">array : 'T[]</span></span>

<span data-ttu-id="3b4bc-108">Arama işlevi olarak temsil edilecek dizi.</span><span class="sxs-lookup"><span data-stu-id="3b4bc-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="3b4bc-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="3b4bc-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="3b4bc-110">Bunun `f` gibi bir işlev `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="3b4bc-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3b4bc-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="3b4bc-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3b4bc-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="3b4bc-112">'T</span></span>

<span data-ttu-id="3b4bc-113">Arama işlevi olarak temsil edilen dizinin öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="3b4bc-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b4bc-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3b4bc-114">Remarks</span></span>

<span data-ttu-id="3b4bc-115">Bu işlev, işlevleri bağımsız değişkenleri olarak alan işlevler ve işlemlerle birlikte çalışmak için genellikle faydalıdır `Int -> 'T` .</span><span class="sxs-lookup"><span data-stu-id="3b4bc-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="3b4bc-116">Bu, örneğin, bir diziyi belleğin tamamına kaydetme gereksinimini ortadan kaldırmak için işlevin kullanıldığı Oluşturucu temsili kitaplığı içinde yaygın olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="3b4bc-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>