---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: faca9b3f6d9a132b591a532c9e2ce54af1f0b182
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218946"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="7e22b-102">ApplyCurriedOpC işlemi</span><span class="sxs-lookup"><span data-stu-id="7e22b-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="7e22b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7e22b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7e22b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e22b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7e22b-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="7e22b-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="7e22b-106">curriedOp: 'T-> ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="7e22b-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="7e22b-107">ilk: 'T</span><span class="sxs-lookup"><span data-stu-id="7e22b-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="7e22b-108">İkinci: ' U</span><span class="sxs-lookup"><span data-stu-id="7e22b-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="7e22b-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7e22b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7e22b-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7e22b-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7e22b-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="7e22b-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="7e22b-112">' U</span><span class="sxs-lookup"><span data-stu-id="7e22b-112">'U</span></span>

