---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727247"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="82cf3-102">EqualityFactB işlevi</span><span class="sxs-lookup"><span data-stu-id="82cf3-102">EqualityFactB function</span></span>

<span data-ttu-id="82cf3-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="82cf3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="82cf3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82cf3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82cf3-105">Klasik bir bool değişkeninin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="82cf3-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="82cf3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="82cf3-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="82cf3-107">gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="82cf3-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82cf3-108">Denetlenecek değişken.</span><span class="sxs-lookup"><span data-stu-id="82cf3-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="82cf3-109">beklenen: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="82cf3-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82cf3-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="82cf3-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="82cf3-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="82cf3-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="82cf3-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="82cf3-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="82cf3-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="82cf3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
