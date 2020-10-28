---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 34bb38a9447f71372ec0b234731f31a5818d3af1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727241"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="857c9-102">EqualityFactI işlevi</span><span class="sxs-lookup"><span data-stu-id="857c9-102">EqualityFactI function</span></span>

<span data-ttu-id="857c9-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="857c9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="857c9-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="857c9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="857c9-105">Klasik bir INT değişkeninin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="857c9-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="857c9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="857c9-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="857c9-107">gerçek: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="857c9-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="857c9-108">Denetlenecek sayı.</span><span class="sxs-lookup"><span data-stu-id="857c9-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="857c9-109">beklenen: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="857c9-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="857c9-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="857c9-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="857c9-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="857c9-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="857c9-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="857c9-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="857c9-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="857c9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

