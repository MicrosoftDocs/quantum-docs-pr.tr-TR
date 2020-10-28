---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: Miktar Tumwalkbyqubitişleştirme işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734119"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="4e330-102">Miktar Tumwalkbyqubitişleştirme işlevi</span><span class="sxs-lookup"><span data-stu-id="4e330-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="4e330-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4e330-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4e330-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e330-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e330-105">Blok kodlama yansımasını bir hisse mühendisiye dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="4e330-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="4e330-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4e330-106">Description</span></span>

<span data-ttu-id="4e330-107">Belirli bir `BlockEncodingReflection` operatör $H $ ' i kodlayan bir Unitary $U $ tarafından temsil edilen bir işlem, bu dosyayı $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ alanını içeren bir hisse alım $W $ değerine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="4e330-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="4e330-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="4e330-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="4e330-109">Blockenkodlama: [Blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="4e330-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="4e330-110">`BlockEncodingReflection`Hisse için bir $U $.</span><span class="sxs-lookup"><span data-stu-id="4e330-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="4e330-111">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="4e330-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4e330-112">Bir hisse alım $W $, Yazmaçlarda ortaklaşa bulunan `a` ve `s` Bu blok-kodlama $H $ ve $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ yelpazesini içerir.</span><span class="sxs-lookup"><span data-stu-id="4e330-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="4e330-113">Referanslar</span><span class="sxs-lookup"><span data-stu-id="4e330-113">References</span></span>

- <span data-ttu-id="4e330-114">Hamiltonian simülasyonu, Qubitiş, Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="4e330-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="4e330-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4e330-115">See Also</span></span>

- [<span data-ttu-id="4e330-116">Microsoft. hisse. simülasyon. Blockenkodlama</span><span class="sxs-lookup"><span data-stu-id="4e330-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="4e330-117">Microsoft. hisse. simülasyon. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="4e330-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)