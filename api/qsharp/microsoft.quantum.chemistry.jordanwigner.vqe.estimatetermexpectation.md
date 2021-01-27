---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Estimatetermexeditation işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835665"
---
# <a name="estimatetermexpectation-operation"></a>Estimatetermexeditation işlemi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Belirli bir Jordan-Wigner Hamiltonian terimiyle ilişkili enerjiyi hesaplar

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Description

Bu işlem, her ölçüm işleciyle ilişkili beklenerek değeri tahmin eder ve örnekleme kullanarak karşılık gelen katsayısı ile çarpar.
Sonuçlar, Jordan-Wigner teriminin enerji düzeyini içeren bir değişkende toplanır.

## <a name="input"></a>Giriş

### <a name="inputstateunitary--qubit--unit--is-adj"></a>ınputstateunitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Durum hazırlığı için kullanılan Unitary.


### <a name="ops--pauli"></a>Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Jordan-Wigner teriminin ölçüm işleçleri.


### <a name="coeffs--double"></a>coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]

Jordan-Wigner teriminin katsayısıdır.


### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Molesel sistemin benzetimini yapmak için gereken qubit sayısı.


### <a name="nsamples--int"></a>nSamples: [Int](xref:microsoft.quantum.lang-ref.int)

Beklenme teriminin tahmini için kullanılacak örneklerin sayısı.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

Jordan-Wigner terimiyle ilişkilendirilen enerji.