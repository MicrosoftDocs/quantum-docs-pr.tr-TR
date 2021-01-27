---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: Hazırlık Esparsemulticonfigurationalstate işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 49b93d0f2447e9eee503bb6ee26aef46c4f5e3f2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98836057"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a><span data-ttu-id="47f84-102">Hazırlık Esparsemulticonfigurationalstate işlemi</span><span class="sxs-lookup"><span data-stu-id="47f84-102">PrepareSparseMultiConfigurationalState operation</span></span>

<span data-ttu-id="47f84-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="47f84-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="47f84-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="47f84-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="47f84-105">İlk deneme durumuna exalıntılar ekleyerek deneme durumuna ait seyrek bir çok yapılandırılazi durumu hazırlama.</span><span class="sxs-lookup"><span data-stu-id="47f84-105">Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.</span></span>

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="47f84-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="47f84-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="47f84-107">ınitialstatehazırlama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47f84-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="47f84-108">İlk deneme durumunu hazırlamak için Unitary.</span><span class="sxs-lookup"><span data-stu-id="47f84-108">Unitary to prepare initial trial state.</span></span>


### <a name="excitations--jordanwignerinputstate"></a><span data-ttu-id="47f84-109">exalıntılar: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="47f84-109">excitations : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="47f84-110">Exalıntılar 'ın ve nalıntı 'nin üzerinde hareket ettiği qubit dizinlerinin genliğini temsil eden ilk deneme durumunun ayıklanma sayısı.</span><span class="sxs-lookup"><span data-stu-id="47f84-110">Excitations of initial trial state represented by the amplitude of the excitation and the qubit indices the excitation acts on.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="47f84-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="47f84-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="47f84-112">Hamiltonian, qubit.</span><span class="sxs-lookup"><span data-stu-id="47f84-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="47f84-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47f84-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

