---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: 65e861914b57cf8a32f2321f881248830b72c54e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841901"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="7300d-102">ApplyCurriedOpC işlemi</span><span class="sxs-lookup"><span data-stu-id="7300d-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="7300d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7300d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7300d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7300d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7300d-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="7300d-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="7300d-106">curriedOp: 'T-> ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="7300d-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="7300d-107">ilk: 'T</span><span class="sxs-lookup"><span data-stu-id="7300d-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="7300d-108">İkinci: ' U</span><span class="sxs-lookup"><span data-stu-id="7300d-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="7300d-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7300d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7300d-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7300d-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7300d-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="7300d-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="7300d-112">' U</span><span class="sxs-lookup"><span data-stu-id="7300d-112">'U</span></span>

