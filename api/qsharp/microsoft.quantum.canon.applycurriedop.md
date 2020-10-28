---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: 22e2ace51175ed9df1c70bf75ce2b497f8449020
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729663"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="c7140-102">ApplyCurriedOp işlemi</span><span class="sxs-lookup"><span data-stu-id="c7140-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="c7140-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c7140-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c7140-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7140-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="c7140-105">Giriş</span><span class="sxs-lookup"><span data-stu-id="c7140-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="c7140-106">curriedOp: 'T-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7140-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="c7140-107">ilk: 'T</span><span class="sxs-lookup"><span data-stu-id="c7140-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="c7140-108">İkinci: ' U</span><span class="sxs-lookup"><span data-stu-id="c7140-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="c7140-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c7140-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c7140-110">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c7140-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c7140-111">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c7140-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="c7140-112">' U</span><span class="sxs-lookup"><span data-stu-id="c7140-112">'U</span></span>

