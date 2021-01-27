---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 9bf42131860b9fe9bd223ade32f95ec747abefe8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854375"
---
# <a name="prepareentangledstate-operation"></a>PrepareEntangledState işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İkili entangles iki qubit kaydı.

Diğer bir deyişle, iki kayıt söz konusu olduğunda, {1} {2} {00} {11} her kaydın $ \ket{0\cnoktalar 0} $ durumunda başlayacağını varsayarak, her bir kasadaki her bir qubit çifti arasında en yüksek düzeyde entangled State $ \frac {\sqrt} \left (\ment + \ket \ right) $ değerini hazırlar.

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="left--qubit"></a>Sol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi


### <a name="right--qubit"></a>right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

