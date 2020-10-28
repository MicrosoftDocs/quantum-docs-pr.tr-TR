---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727205"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="e1057-102">FormattedFailure işlevi</span><span class="sxs-lookup"><span data-stu-id="e1057-102">FormattedFailure function</span></span>

<span data-ttu-id="e1057-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e1057-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e1057-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1057-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1057-105">Anlamlı hata iletileriyle başarısız olmak için kullanılan iç işlev.</span><span class="sxs-lookup"><span data-stu-id="e1057-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e1057-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e1057-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="e1057-107">gerçek: 'T</span><span class="sxs-lookup"><span data-stu-id="e1057-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="e1057-108">beklenen: 'T</span><span class="sxs-lookup"><span data-stu-id="e1057-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="e1057-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e1057-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="e1057-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1057-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e1057-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e1057-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1057-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e1057-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="e1057-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e1057-113">Remarks</span></span>

<span data-ttu-id="e1057-114">Bu işlevin simülasyonu çalışma zamanları tarafından öykünmek üzere tasarlanmıştır. bu nedenle, biçimlendirilen çelişmeleri iletmeyi sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="e1057-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>