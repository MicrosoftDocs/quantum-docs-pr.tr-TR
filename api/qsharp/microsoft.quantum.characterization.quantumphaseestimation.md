---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Miktar Tumphasetahmin işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 7e524477a4b2bcd8d6767441e278fbf501355e0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728177"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="35f63-102">Miktar Tumphasetahmin işlemi</span><span class="sxs-lookup"><span data-stu-id="35f63-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="35f63-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="35f63-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="35f63-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35f63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35f63-105">Belirli bir Oracle `U` ve `targetState` aşamayı bir büyük endian hisse kaydına okumak için hisse aşaması tahmin algoritmasını gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="35f63-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="35f63-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="35f63-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="35f63-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="35f63-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="35f63-108">Verilen tamsayı güçleri için $U ^ d $ uygulayan bir işlem.</span><span class="sxs-lookup"><span data-stu-id="35f63-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="35f63-109">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="35f63-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="35f63-110">$ \Ket{\phi} $ durumunu temsil eden bir hisse kaydı $U $ tarafından kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="35f63-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="35f63-111">$ \Ket{\phi} $ bir $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \fi \ [0, 2 \ Pi) $ bilinmeyen bir aşama.</span><span class="sxs-lookup"><span data-stu-id="35f63-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="35f63-112">controlRegister: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="35f63-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="35f63-113">Belirtilen Oracle 'ı denetlemek için kullanılabilen ve bu işlemin uygulamadan sonraki $ \phi $ gösterimini içeren büyük endian temsili tamsayı kaydı.</span><span class="sxs-lookup"><span data-stu-id="35f63-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="35f63-114">ControlRegister 'ın, kayıt uzunluğunun istenen hassasiyetini gösterdiği ilk durum olan $ \ket{00\cnoktalar 0} $ başlangıç durumunda başlaması varsayılır.</span><span class="sxs-lookup"><span data-stu-id="35f63-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="35f63-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="35f63-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

