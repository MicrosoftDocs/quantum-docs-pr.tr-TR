---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Hazırlık Esparsemulticonfigurationalstate işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 4d39be70c48ed49a1eec410ed6f8e5081dc1e8ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224777"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="94a3d-102">Hazırlık Esparsemulticonfigurationalstate işlemi</span><span class="sxs-lookup"><span data-stu-id="94a3d-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="94a3d-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="94a3d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="94a3d-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="94a3d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="94a3d-105">İlk deneme durumuna exalıntılar ekleyerek deneme durumuna ait seyrek bir çok yapılandırılazi durumu hazırlama.</span><span class="sxs-lookup"><span data-stu-id="94a3d-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="94a3d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="94a3d-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="94a3d-107">ınitialstatehazırlama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94a3d-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="94a3d-108">İlk deneme durumunu hazırlamak için Unitary.</span><span class="sxs-lookup"><span data-stu-id="94a3d-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="94a3d-109">exalıntılar: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="94a3d-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="94a3d-110">Exalıntılar 'ın ve nalıntı 'nin üzerinde hareket ettiği qubit dizinlerinin genliğini temsil eden ilk deneme durumunun ayıklanma sayısı.</span><span class="sxs-lookup"><span data-stu-id="94a3d-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="94a3d-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="94a3d-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="94a3d-112">Hamiltonian, qubit.</span><span class="sxs-lookup"><span data-stu-id="94a3d-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="94a3d-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94a3d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

