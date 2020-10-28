---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: bfd7b9ce8e8b2c8f322d676c640f8c2488655516
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727668"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="bcd0f-102">_prepareTrialStateWrapper işlemi</span><span class="sxs-lookup"><span data-stu-id="bcd0f-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="bcd0f-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="bcd0f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="bcd0f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bcd0f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bcd0f-105">Özel sarmalayıcı bir adjoint tanımlayarak EstimateFrequencyA ile uyumlu hale getirmek için Etrialstate.</span><span class="sxs-lookup"><span data-stu-id="bcd0f-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="bcd0f-106">EstimateFrequencyA, miktarını hızlandıran, Hislatör simülatörünü hedeflerken yerleşik öykünme özelliğine sahiptir.</span><span class="sxs-lookup"><span data-stu-id="bcd0f-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="bcd0f-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="bcd0f-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="bcd0f-108">ınputstate: ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span><span class="sxs-lookup"><span data-stu-id="bcd0f-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="bcd0f-109">Hazırlık Etrialstate 'in çalışması için gereken Jordan-Wigner girişi.</span><span class="sxs-lookup"><span data-stu-id="bcd0f-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="bcd0f-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bcd0f-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bcd0f-111">Bir qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="bcd0f-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bcd0f-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bcd0f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

