---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733602"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="5dd81-102">SetToBasisState işlemi</span><span class="sxs-lookup"><span data-stu-id="5dd81-102">SetToBasisState operation</span></span>

<span data-ttu-id="5dd81-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="5dd81-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="5dd81-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5dd81-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5dd81-105">Qubit ' i ölçerek ve gerekirse bir bit çevirme uygulayarak belirli bir hesaplama tabanlı duruma bir qubit ayarlar.</span><span class="sxs-lookup"><span data-stu-id="5dd81-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5dd81-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5dd81-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="5dd81-107">istenen: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="5dd81-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="5dd81-108">Qubitin olarak ayarlanması gereken temel durum.</span><span class="sxs-lookup"><span data-stu-id="5dd81-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="5dd81-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5dd81-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5dd81-110">Durumu ayarlanacak qubit.</span><span class="sxs-lookup"><span data-stu-id="5dd81-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5dd81-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5dd81-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5dd81-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5dd81-112">Remarks</span></span>

<span data-ttu-id="5dd81-113">Bu işlemin bir sabiti olarak, `M(q)` hemen sonrasında çağırma `SetToBasisState(result, q)` geri döndürülür `result` .</span><span class="sxs-lookup"><span data-stu-id="5dd81-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>