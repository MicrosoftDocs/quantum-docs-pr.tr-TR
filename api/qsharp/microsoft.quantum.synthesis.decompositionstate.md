---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Dekompozisyontionstate Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733911"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="a25fa-102">Dekompozisyontionstate Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="a25fa-102">DecompositionState user defined type</span></span>

<span data-ttu-id="a25fa-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a25fa-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a25fa-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a25fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a25fa-105">Değişken dizinleri temel alarak ayrıştırma sırasında durum</span><span class="sxs-lookup"><span data-stu-id="a25fa-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="a25fa-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="a25fa-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="a25fa-107">İzin: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a25fa-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="a25fa-108">Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="a25fa-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="a25fa-109">Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="a25fa-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="a25fa-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="a25fa-110">Description</span></span>

<span data-ttu-id="a25fa-111">Durum, sol taraftaki kontrol edilen kapıların ve sağ taraftaki denetimli kapıların geçerli permütasyon ve şu anda oluşturulmuş işlevlerini barındırır.</span><span class="sxs-lookup"><span data-stu-id="a25fa-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>