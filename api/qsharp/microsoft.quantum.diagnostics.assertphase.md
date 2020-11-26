---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202269"
---
# <a name="assertphase-operation"></a><span data-ttu-id="033c1-102">AssertPhase işlemi</span><span class="sxs-lookup"><span data-stu-id="033c1-102">AssertPhase operation</span></span>

<span data-ttu-id="033c1-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="033c1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="033c1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="033c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="033c1-105">Bir eşit üst konum durumunun beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="033c1-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="033c1-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="033c1-106">Description</span></span>

<span data-ttu-id="033c1-107">Bu işlem, bazı rastgele gerçek $t $ için beklenen değere sahip $ \frac{e ^ {ı t}} {\sqrt {2} } (e ^ {i\phi} \ demet {0} + e ^ {-i\phi} \ ayraç {1} ) $ olarak ifade edilen bir hisse cısının $ \phi $ aşamasını onaylar</span><span class="sxs-lookup"><span data-stu-id="033c1-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="033c1-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="033c1-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="033c1-109">beklenen: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="033c1-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="033c1-110">$ \Phi \ in (-\pı, \pı] $ değerinin beklenen değeri.</span><span class="sxs-lookup"><span data-stu-id="033c1-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="033c1-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="033c1-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="033c1-112">Beklenen durumu depolayan qubit.</span><span class="sxs-lookup"><span data-stu-id="033c1-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="033c1-113">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="033c1-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="033c1-114">Gerçek ve beklenen arasındaki fark için mutlak tolerans.</span><span class="sxs-lookup"><span data-stu-id="033c1-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="033c1-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="033c1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

