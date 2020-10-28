---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: Estimatetermexeditation işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727655"
---
# <a name="estimatetermexpectation-operation"></a>Estimatetermexeditation işlemi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Leyebilir [](https://nuget.org/packages/)


Belirli bir Jordan-Wigner Hamiltonian terimiyle ilişkili enerjiyi hesaplar

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>Açıklama

Bu işlem, her ölçüm işleciyle ilişkili beklenerek değeri tahmin eder ve örnekleme kullanarak karşılık gelen katsayısı ile çarpar.
Sonuçlar, Jordan-Wigner teriminin enerji düzeyini içeren bir değişkende toplanır.

## <a name="input"></a>Giriş

### <a name="inputstateunitary--qubit--unit-adj"></a>ınputstateunitary: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama

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