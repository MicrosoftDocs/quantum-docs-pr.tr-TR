---
uid: Microsoft.Quantum.Diagnostics._prepareEntangledState
title: _prepareEntangledState işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _prepareEntangledState
qsharp.summary: >-
  Given two registers, prepares the maximally entangled state between each pair of qubits on the respective registers. All qubits must start in the |0⟩ state.

  The result is that corresponding pairs of qubits from each register are in the $\bra{\beta_{00}}\ket{\beta_{00}}$.
ms.openlocfilehash: 384dad5905cec50b500028e1bc352a742122b299
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727398"
---
# <a name="_prepareentangledstate-operation"></a>_prepareEntangledState işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


İki kayıt verildiğinde, ilgili yazmaçlardaki her bir qubit çifti arasında en yüksek düzeyde bir durum hazırlar.
Tüm qubits, | 0 ⟩ durumunda başlamalıdır.

Sonuç olarak her bir kayıttaki karşılık gelen qubit çiftleri $ \bra{\ beta_ {00} } \ket{\ beta_ {00} } $ içinde bulunur.

```qsharp
operation _prepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="left--qubit"></a>Sol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi


### <a name="right--qubit"></a>right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

