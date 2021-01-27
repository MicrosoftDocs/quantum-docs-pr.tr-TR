---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: 100d8a42d6475d3cdda349a2e685a6fbfff23cdc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845086"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="b20ec-102">ApplyCurriedOpA işlemi</span><span class="sxs-lookup"><span data-stu-id="b20ec-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="b20ec-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b20ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b20ec-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b20ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="b20ec-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="b20ec-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="b20ec-106">curriedOp: 'T-> ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="b20ec-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="b20ec-107">ilk: 'T</span><span class="sxs-lookup"><span data-stu-id="b20ec-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="b20ec-108">İkinci: ' U</span><span class="sxs-lookup"><span data-stu-id="b20ec-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="b20ec-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b20ec-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b20ec-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="b20ec-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b20ec-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="b20ec-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="b20ec-112">' U</span><span class="sxs-lookup"><span data-stu-id="b20ec-112">'U</span></span>

