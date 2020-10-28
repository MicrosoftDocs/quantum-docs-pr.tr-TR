---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732175"
---
# <a name="prepareentangledstate-operation"></a>PrepareEntangledState işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Leyebilir [](https://nuget.org/packages/)


İkili entangles iki qubit kaydı.

Diğer bir deyişle, iki kayıt söz konusu olduğunda, {1} {2} {00} {11} her kaydın $ \ket{0\cnoktalar 0} $ durumunda başlayacağını varsayarak, her bir kasadaki her bir qubit çifti arasında en yüksek düzeyde entangled State $ \frac {\sqrt} \left (\ment + \ket \ right) $ değerini hazırlar.

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="left--qubit"></a>Sol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi


### <a name="right--qubit"></a>right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cnoktalar 0} $ durumundaki qubit dizisi



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

