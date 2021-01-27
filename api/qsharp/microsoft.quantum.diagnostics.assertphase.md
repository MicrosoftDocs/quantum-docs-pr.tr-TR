---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830073"
---
# <a name="assertphase-operation"></a><span data-ttu-id="89575-102">AssertPhase işlemi</span><span class="sxs-lookup"><span data-stu-id="89575-102">AssertPhase operation</span></span>

<span data-ttu-id="89575-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="89575-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="89575-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89575-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89575-105">Bir eşit üst konum durumunun beklenen değere sahip olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="89575-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="89575-106">Description</span><span class="sxs-lookup"><span data-stu-id="89575-106">Description</span></span>

<span data-ttu-id="89575-107">Bu işlem, bazı rastgele gerçek $t $ için beklenen değere sahip $ \frac{e ^ {ı t}} {\sqrt {2} } (e ^ {i\phi} \ demet {0} + e ^ {-i\phi} \ ayraç {1} ) $ olarak ifade edilen bir hisse cısının $ \phi $ aşamasını onaylar</span><span class="sxs-lookup"><span data-stu-id="89575-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="89575-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="89575-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="89575-109">beklenen: [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="89575-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="89575-110">$ \Phi \ in (-\pı, \pı] $ değerinin beklenen değeri.</span><span class="sxs-lookup"><span data-stu-id="89575-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="89575-111">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="89575-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="89575-112">Beklenen durumu depolayan qubit.</span><span class="sxs-lookup"><span data-stu-id="89575-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="89575-113">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="89575-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="89575-114">Gerçek ve beklenen arasındaki fark için mutlak tolerans.</span><span class="sxs-lookup"><span data-stu-id="89575-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="89575-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89575-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="89575-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="89575-116">Example</span></span>

<span data-ttu-id="89575-117">Şu onay başarılı oldu: `qubit` durum $ \ket{\psı} = e ^ {i 0,5} \ sqrt {1/2} \ demet {0} + e ^ {i 0,5} \ sqrt {1/2} \ demet {1} $;</span><span class="sxs-lookup"><span data-stu-id="89575-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="89575-118">`qubit` State $ \ket{\psı} = e ^ {i 0,5} \ sqrt {1/2} \ demet {0} + e ^ {-i 0,5} \ sqrt {1/2} \ demet {1} $;</span><span class="sxs-lookup"><span data-stu-id="89575-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="89575-119">`qubit` State $ \ket{\psı} = e ^ {-i 2.2} \ sqrt {1/2} \ {0} Tus+ e ^ {i 0.2} \ sqrt {1/2} \ demet {1} $;</span><span class="sxs-lookup"><span data-stu-id="89575-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`