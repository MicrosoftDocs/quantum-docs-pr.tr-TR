---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727374"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="76f40-102">AllEqualityFactB işlevi</span><span class="sxs-lookup"><span data-stu-id="76f40-102">AllEqualityFactB function</span></span>

<span data-ttu-id="76f40-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="76f40-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="76f40-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76f40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76f40-105">İki dizi Boole değerinin eşit olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="76f40-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="76f40-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="76f40-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="76f40-107">gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="76f40-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="76f40-108">İlgilendiğiniz bir test çalışması tarafından üretilen dizi.</span><span class="sxs-lookup"><span data-stu-id="76f40-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="76f40-109">beklenen: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="76f40-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="76f40-110">İlgilendiğiniz test durumundan beklenen dizi.</span><span class="sxs-lookup"><span data-stu-id="76f40-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="76f40-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="76f40-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="76f40-112">Diziler eşit değilse yazdırılacak bir ileti.</span><span class="sxs-lookup"><span data-stu-id="76f40-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="76f40-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76f40-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
