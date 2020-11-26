---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 9b17bac9d95baf5a542604892c64130bf35d7f69
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202439"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


İki işlem söz konusu olduğunda, tüm giriş durumları için aynı hareket ettikleri onaylar.

Bu onaylama, formun tüm durumlarında işlem eylemi $V _0 \otimes... V_ {n-1} $, $V _k $ durumlardan biri $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ ve $ \ket{i} $ (Pauli Y işlecinin 1 eigenstate)

Bu onaylama $n $ qubits kullanır ve karşılaştırılmakta olan işlemlere yönelik birden çok çağrı gerektirir.

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

İşlemler `givenU` ve üzerinde çalışan qubits $n $ sayısı `expectedU` .


### <a name="givenu--qubit--unit"></a>givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit) 

$N $ qubits üzerinde işlem denetlenecek.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

İle Karşılaştırılacak $n $ qubit üzerinde başvuru işlemi `givenU` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Başvurular

$ \Ket {0} $, $ \ket {1} $, $ \ket{+} $ ve $ \ket{i} $ durumlarının temeli [ *i. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001)bölümünde açıklanan Chuang-Nielsen temelidir.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Diagnostics. AssertOperationsEqualReferenced](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)