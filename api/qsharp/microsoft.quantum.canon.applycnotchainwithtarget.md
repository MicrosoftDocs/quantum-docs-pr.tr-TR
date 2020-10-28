---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729679"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="8df1c-102">ApplyCNOTChainWithTarget işlemi</span><span class="sxs-lookup"><span data-stu-id="8df1c-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="8df1c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8df1c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8df1c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8df1c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8df1c-105">Bir qubits dizisinin bir hedef qubit 'e eşlik durumunu hesaplar.</span><span class="sxs-lookup"><span data-stu-id="8df1c-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="8df1c-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="8df1c-106">Description</span></span>

<span data-ttu-id="8df1c-107">Dizi başlangıçta $ \ket{q_0} \ket{q_1} \cnoktalar \ket{q_ {\Text{Target}}} $ durumunda ise, son durum $ \ket{q_0} \ket{q_1 \oplus q_0} \cnoktalar \ket{q_ {n-1} \oplus \cnoktalar \oplus q_0 \oplus q_ {\Text{Target}}} $ tarafından verilir.</span><span class="sxs-lookup"><span data-stu-id="8df1c-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="8df1c-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="8df1c-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="8df1c-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8df1c-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8df1c-110">Eşlik öğesinin hesaplandığı qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="8df1c-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="8df1c-111">targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8df1c-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8df1c-112">' Qubits ' öğesinin eşliği XORed olduğu son qubit.</span><span class="sxs-lookup"><span data-stu-id="8df1c-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8df1c-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8df1c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8df1c-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8df1c-114">Remarks</span></span>

<span data-ttu-id="8df1c-115">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="8df1c-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="8df1c-116">ve</span><span class="sxs-lookup"><span data-stu-id="8df1c-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```