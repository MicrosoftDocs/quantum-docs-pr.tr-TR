---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 725291e8b5d12683ad580d5938dadd561831e88e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853552"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="05ebc-102">AllEqualityFactB işlevi</span><span class="sxs-lookup"><span data-stu-id="05ebc-102">AllEqualityFactB function</span></span>

<span data-ttu-id="05ebc-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="05ebc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="05ebc-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05ebc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05ebc-105">İki dizi Boole değerinin eşit olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="05ebc-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="05ebc-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="05ebc-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="05ebc-107">gerçek: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="05ebc-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="05ebc-108">İlgilendiğiniz bir test çalışması tarafından üretilen dizi.</span><span class="sxs-lookup"><span data-stu-id="05ebc-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="05ebc-109">beklenen: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="05ebc-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="05ebc-110">İlgilendiğiniz test durumundan beklenen dizi.</span><span class="sxs-lookup"><span data-stu-id="05ebc-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="05ebc-111">ileti: [dize](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="05ebc-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="05ebc-112">Diziler eşit değilse yazdırılacak bir ileti.</span><span class="sxs-lookup"><span data-stu-id="05ebc-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="05ebc-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="05ebc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

