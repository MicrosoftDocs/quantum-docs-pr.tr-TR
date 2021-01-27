---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: Miktar Tumwalkbyqubitişleştirme işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: 8ffb6eb77a3f910d3064c4a3c90215d5d9a694aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851050"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="ec223-102">Miktar Tumwalkbyqubitişleştirme işlevi</span><span class="sxs-lookup"><span data-stu-id="ec223-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="ec223-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="ec223-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="ec223-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec223-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec223-105">Blok kodlama yansımasını bir hisse mühendisiye dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="ec223-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="ec223-106">Description</span><span class="sxs-lookup"><span data-stu-id="ec223-106">Description</span></span>

<span data-ttu-id="ec223-107">Belirli bir `BlockEncodingReflection` operatör $H $ ' i kodlayan bir Unitary $U $ tarafından temsil edilen bir işlem, bu dosyayı $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ alanını içeren bir hisse alım $W $ değerine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="ec223-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="ec223-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="ec223-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="ec223-109">Blockenkodlama: [Blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="ec223-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="ec223-110">`BlockEncodingReflection`Hisse için bir $U $.</span><span class="sxs-lookup"><span data-stu-id="ec223-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="ec223-111">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="ec223-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ec223-112">Bir hisse alım $W $, Yazmaçlarda ortaklaşa bulunan `a` ve `s` Bu blok-kodlama $H $ ve $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ yelpazesini içerir.</span><span class="sxs-lookup"><span data-stu-id="ec223-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="ec223-113">Başvurular</span><span class="sxs-lookup"><span data-stu-id="ec223-113">References</span></span>

- <span data-ttu-id="ec223-114">Hamiltonian simülasyonu, Qubitiş, Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="ec223-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="ec223-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ec223-115">See Also</span></span>

- [<span data-ttu-id="ec223-116">Microsoft. hisse. simülasyon. Blockenkodlama</span><span class="sxs-lookup"><span data-stu-id="ec223-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="ec223-117">Microsoft. hisse. simülasyon. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="ec223-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)