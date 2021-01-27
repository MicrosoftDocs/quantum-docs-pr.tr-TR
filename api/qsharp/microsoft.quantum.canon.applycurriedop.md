---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: c252eceb6a307ea9514aaa8aa3a3de1f9fa1b698
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841928"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="cdd92-102">ApplyCurriedOp işlemi</span><span class="sxs-lookup"><span data-stu-id="cdd92-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="cdd92-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cdd92-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cdd92-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cdd92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="cdd92-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="cdd92-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="cdd92-106">curriedOp: 'T-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdd92-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="cdd92-107">ilk: 'T</span><span class="sxs-lookup"><span data-stu-id="cdd92-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="cdd92-108">İkinci: ' U</span><span class="sxs-lookup"><span data-stu-id="cdd92-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="cdd92-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdd92-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cdd92-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="cdd92-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cdd92-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="cdd92-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="cdd92-112">' U</span><span class="sxs-lookup"><span data-stu-id="cdd92-112">'U</span></span>

