---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732146"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="1b59e-102">ApplyBlockEncodingByLCU işlemi</span><span class="sxs-lookup"><span data-stu-id="1b59e-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="1b59e-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="1b59e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="1b59e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1b59e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1b59e-105">Uygulamasının uygulamasıdır `BlockEncodingByLCU` .</span><span class="sxs-lookup"><span data-stu-id="1b59e-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a><span data-ttu-id="1b59e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1b59e-106">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="1b59e-107">Statehazırlama: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="1b59e-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="1b59e-108">seçici: ('T, 'S) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="1b59e-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="1b59e-109">yardımcı: 'T</span><span class="sxs-lookup"><span data-stu-id="1b59e-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="1b59e-110">Sistem: 'S</span><span class="sxs-lookup"><span data-stu-id="1b59e-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="1b59e-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1b59e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1b59e-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="1b59e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b59e-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="1b59e-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="1b59e-114">Üreticinin</span><span class="sxs-lookup"><span data-stu-id="1b59e-114">'S</span></span>

