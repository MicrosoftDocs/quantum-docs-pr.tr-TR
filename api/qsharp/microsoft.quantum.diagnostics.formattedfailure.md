---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201708"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="1568f-102">FormattedFailure işlevi</span><span class="sxs-lookup"><span data-stu-id="1568f-102">FormattedFailure function</span></span>

<span data-ttu-id="1568f-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1568f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1568f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1568f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1568f-105">Anlamlı hata iletileriyle başarısız olmak için kullanılan iç işlev.</span><span class="sxs-lookup"><span data-stu-id="1568f-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1568f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1568f-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="1568f-107">gerçek: 'T</span><span class="sxs-lookup"><span data-stu-id="1568f-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="1568f-108">beklenen: 'T</span><span class="sxs-lookup"><span data-stu-id="1568f-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="1568f-109">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1568f-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="1568f-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1568f-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1568f-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="1568f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1568f-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="1568f-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="1568f-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1568f-113">Remarks</span></span>

<span data-ttu-id="1568f-114">Bu işlevin simülasyonu çalışma zamanları tarafından öykünmek üzere tasarlanmıştır. bu nedenle, biçimlendirilen çelişmeleri iletmeyi sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="1568f-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>