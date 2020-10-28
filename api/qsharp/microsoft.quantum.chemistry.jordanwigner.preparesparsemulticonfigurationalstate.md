---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Hazırlık Esparsemulticonfigurationalstate işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 1182f79a33784cdb49cb13db5cc97a0a45e59f9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727704"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="2818c-102">Hazırlık Esparsemulticonfigurationalstate işlemi</span><span class="sxs-lookup"><span data-stu-id="2818c-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="2818c-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="2818c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="2818c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2818c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2818c-105">İlk deneme durumuna exalıntılar ekleyerek deneme durumuna ait seyrek bir çok yapılandırılazi durumu hazırlama.</span><span class="sxs-lookup"><span data-stu-id="2818c-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2818c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2818c-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="2818c-107">ınitialstatehazırlama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2818c-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2818c-108">İlk deneme durumunu hazırlamak için Unitary.</span><span class="sxs-lookup"><span data-stu-id="2818c-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="2818c-109">exalıntılar: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="2818c-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="2818c-110">Exalıntılar 'ın ve nalıntı 'nin üzerinde hareket ettiği qubit dizinlerinin genliğini temsil eden ilk deneme durumunun ayıklanma sayısı.</span><span class="sxs-lookup"><span data-stu-id="2818c-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2818c-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2818c-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2818c-112">Hamiltonian, qubit.</span><span class="sxs-lookup"><span data-stu-id="2818c-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2818c-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2818c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

