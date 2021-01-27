---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829136"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="6468b-102">EqualityFactL işlevi</span><span class="sxs-lookup"><span data-stu-id="6468b-102">EqualityFactL function</span></span>

<span data-ttu-id="6468b-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6468b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6468b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6468b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6468b-105">Klasik bir BigInt değişkeninin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="6468b-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6468b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6468b-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="6468b-107">gerçek: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6468b-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6468b-108">Denetlenecek sayı.</span><span class="sxs-lookup"><span data-stu-id="6468b-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="6468b-109">beklenen: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6468b-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6468b-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="6468b-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="6468b-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6468b-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6468b-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="6468b-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6468b-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6468b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

