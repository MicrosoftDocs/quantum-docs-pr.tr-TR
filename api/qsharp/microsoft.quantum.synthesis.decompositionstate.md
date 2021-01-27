---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Dekompozisyontionstate Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: eb2aed53b4116a4ea72ee732ff46c4a10eb3d67b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855514"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="e06e1-102">Dekompozisyontionstate Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="e06e1-102">DecompositionState user defined type</span></span>

<span data-ttu-id="e06e1-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e06e1-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e06e1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e06e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e06e1-105">Değişken dizinleri temel alarak ayrıştırma sırasında durum</span><span class="sxs-lookup"><span data-stu-id="e06e1-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="e06e1-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="e06e1-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="e06e1-107">İzin: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e06e1-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="e06e1-108">Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="e06e1-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="e06e1-109">Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="e06e1-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="e06e1-110">Description</span><span class="sxs-lookup"><span data-stu-id="e06e1-110">Description</span></span>

<span data-ttu-id="e06e1-111">Durum, sol taraftaki kontrol edilen kapıların ve sağ taraftaki denetimli kapıların geçerli permütasyon ve şu anda oluşturulmuş işlevlerini barındırır.</span><span class="sxs-lookup"><span data-stu-id="e06e1-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>