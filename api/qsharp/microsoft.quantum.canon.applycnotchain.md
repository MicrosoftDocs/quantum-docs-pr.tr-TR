---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: c98fe24ca352952162acb7a9c4fc93d5da4285b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729687"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="ce3e8-102">ApplyCNOTChain işlemi</span><span class="sxs-lookup"><span data-stu-id="ce3e8-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="ce3e8-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce3e8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce3e8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ce3e8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ce3e8-105">Bir qubits kaydının bir yerinde olan eşlik düzeyini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="ce3e8-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ce3e8-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ce3e8-106">Description</span></span>

<span data-ttu-id="ce3e8-107">Bu işlem girişinin durumunu $ $ \begin{hizalaması} \ket{q_0} \ket{q_1} \cnoktalar \ket{q_ {n-1}} & \mapsto \ket{q_0 olarak dönüştürür} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cnoktalar \ket{q_0 \oplus \cnoktalara \oplus q_ {n-1}}.</span><span class="sxs-lookup"><span data-stu-id="ce3e8-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="ce3e8-108">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="ce3e8-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="ce3e8-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="ce3e8-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="ce3e8-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce3e8-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ce3e8-111">Eşliği hesaplanmak ve depolanacak qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="ce3e8-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce3e8-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce3e8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

