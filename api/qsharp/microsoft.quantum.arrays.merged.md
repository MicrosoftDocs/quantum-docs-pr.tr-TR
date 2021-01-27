---
uid: Microsoft.Quantum.Arrays.Merged
title: Birleştirilmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845619"
---
# <a name="merged-function"></a><span data-ttu-id="f4708-102">Birleştirilmiş işlev</span><span class="sxs-lookup"><span data-stu-id="f4708-102">Merged function</span></span>

<span data-ttu-id="f4708-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f4708-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f4708-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f4708-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f4708-105">İki sıralanmış dizi verildiğinde, her ikisi de sıralanmış düzende öğelerinin bulunduğu tek bir dizi döndürür.</span><span class="sxs-lookup"><span data-stu-id="f4708-105">Given two sorted arrays, returns a single array containing the elements of both in sorted order.</span></span> <span data-ttu-id="f4708-106">Birleştirme sıralaması tarafından dahili olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="f4708-106">Used internally by merge sort.</span></span>

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f4708-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="f4708-107">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="f4708-108">Karşılaştırma: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f4708-108">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="f4708-109">Sol: 'T []</span><span class="sxs-lookup"><span data-stu-id="f4708-109">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="f4708-110">Sağ: 'T []</span><span class="sxs-lookup"><span data-stu-id="f4708-110">right : 'T[]</span></span>





## <a name="output--t"></a><span data-ttu-id="f4708-111">Çıkış: 'T []</span><span class="sxs-lookup"><span data-stu-id="f4708-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f4708-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f4708-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4708-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f4708-113">'T</span></span>

