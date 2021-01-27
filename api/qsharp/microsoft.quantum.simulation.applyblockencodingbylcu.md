---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852821"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="6918e-102">ApplyBlockEncodingByLCU işlemi</span><span class="sxs-lookup"><span data-stu-id="6918e-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="6918e-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6918e-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6918e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6918e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6918e-105">Uygulamasının uygulamasıdır `BlockEncodingByLCU` .</span><span class="sxs-lookup"><span data-stu-id="6918e-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6918e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6918e-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="6918e-107">Statehazırlama: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="6918e-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="6918e-108">seçici: ('T, 'S) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="6918e-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="6918e-109">yardımcı: 'T</span><span class="sxs-lookup"><span data-stu-id="6918e-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="6918e-110">Sistem: 'S</span><span class="sxs-lookup"><span data-stu-id="6918e-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="6918e-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6918e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6918e-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6918e-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6918e-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6918e-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="6918e-114">Üreticinin</span><span class="sxs-lookup"><span data-stu-id="6918e-114">'S</span></span>

