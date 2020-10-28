---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727236"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="1f889-102">EqualityFactL işlevi</span><span class="sxs-lookup"><span data-stu-id="1f889-102">EqualityFactL function</span></span>

<span data-ttu-id="1f889-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1f889-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1f889-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f889-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f889-105">Klasik bir BigInt değişkeninin beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="1f889-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1f889-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1f889-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="1f889-107">gerçek: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1f889-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1f889-108">Denetlenecek sayı.</span><span class="sxs-lookup"><span data-stu-id="1f889-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="1f889-109">beklenen: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1f889-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1f889-110">Beklenen değer.</span><span class="sxs-lookup"><span data-stu-id="1f889-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="1f889-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1f889-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1f889-112">Onaylama tetiklendiğinde kullanılacak hata iletisi dizesi.</span><span class="sxs-lookup"><span data-stu-id="1f889-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f889-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f889-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

