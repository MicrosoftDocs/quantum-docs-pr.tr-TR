---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194160"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="91416-102">SetToBasisState işlemi</span><span class="sxs-lookup"><span data-stu-id="91416-102">SetToBasisState operation</span></span>

<span data-ttu-id="91416-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="91416-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="91416-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="91416-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="91416-105">Qubit ' i ölçerek ve gerekirse bir bit çevirme uygulayarak belirli bir hesaplama tabanlı duruma bir qubit ayarlar.</span><span class="sxs-lookup"><span data-stu-id="91416-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="91416-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="91416-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="91416-107">istenen: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="91416-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="91416-108">Qubitin olarak ayarlanması gereken temel durum.</span><span class="sxs-lookup"><span data-stu-id="91416-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="91416-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="91416-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="91416-110">Durumu ayarlanacak qubit.</span><span class="sxs-lookup"><span data-stu-id="91416-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91416-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91416-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="91416-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="91416-112">Remarks</span></span>

<span data-ttu-id="91416-113">Bu işlemin bir sabiti olarak, `M(q)` hemen sonrasında çağırma `SetToBasisState(result, q)` geri döndürülür `result` .</span><span class="sxs-lookup"><span data-stu-id="91416-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>