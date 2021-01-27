---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: f0deba39d834731fd9057a1d40d0c78b2b7e6bb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850212"
---
# <a name="_preparetrialstatewrapper-operation"></a>_prepareTrialStateWrapper işlemi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Özel sarmalayıcı bir adjoint tanımlayarak EstimateFrequencyA ile uyumlu hale getirmek için Etrialstate.
EstimateFrequencyA, miktarını hızlandıran, Hislatör simülatörünü hedeflerken yerleşik öykünme özelliğine sahiptir.

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="inputstate--intjordanwignerinputstate"></a>ınputstate: ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])

Hazırlık Etrialstate 'in çalışması için gereken Jordan-Wigner girişi.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Bir qubit kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

