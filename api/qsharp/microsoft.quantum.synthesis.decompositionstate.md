---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Dekompozisyontionstate Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: cd2a55013f1232d4158dd6c33143b7cf6c0aafbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203204"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="d4d86-102">Dekompozisyontionstate Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="d4d86-102">DecompositionState user defined type</span></span>

<span data-ttu-id="d4d86-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="d4d86-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="d4d86-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4d86-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4d86-105">Değişken dizinleri temel alarak ayrıştırma sırasında durum</span><span class="sxs-lookup"><span data-stu-id="d4d86-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="d4d86-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="d4d86-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="d4d86-107">İzin: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="d4d86-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="d4d86-108">Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="d4d86-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="d4d86-109">Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="d4d86-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="d4d86-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d4d86-110">Description</span></span>

<span data-ttu-id="d4d86-111">Durum, sol taraftaki kontrol edilen kapıların ve sağ taraftaki denetimli kapıların geçerli permütasyon ve şu anda oluşturulmuş işlevlerini barındırır.</span><span class="sxs-lookup"><span data-stu-id="d4d86-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>