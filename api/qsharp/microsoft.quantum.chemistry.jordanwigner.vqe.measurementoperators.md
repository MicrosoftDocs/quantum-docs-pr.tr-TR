---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 204ae621b77559a894f0bce14e494824d58e4ad6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835391"
---
# <a name="measurementoperators-function"></a>MeasurementOperators işlevi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Bir Jordan-Wigner teriminin beklentisini hesaplamak için gereken tüm ölçüm işleçlerini hesaplar.

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Molesel sistemin benzetimini yapmak için gereken qubit sayısı.


### <a name="indices--int"></a>dizinler: [Int](xref:microsoft.quantum.lang-ref.int)[]

Qubit her Pauli işlecinin dizinlerini içeren bir dizi öğesine uygulanır.


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)

Jordan-Wigner teriminin türü.



## <a name="output--pauli"></a>Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Ölçüm işleçleri dizisi (her biri Pauli dizisi olmak üzere).