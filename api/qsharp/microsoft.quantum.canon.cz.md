---
uid: Microsoft.Quantum.Canon.CZ
title: CZ işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207216"
---
# <a name="cz-operation"></a>CZ işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Denetlenen-Z (CZ) kapısını bir qubit çiftiyle uygular.

$ $ \begin{hizalaması} 1 & 0 & 0 & 0 0 \\ \\ & 1 & 0 & 0 0 & 0 & \\ \\ 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{hizalaması}, $ $ burada satırlar ve sütunlar, hisse kavramları kılavuzunda olduğu gibi düzenlenmiştir.

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="control--qubit"></a>Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)

CZ kapısı için denetim qubit.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

CZ kapısı için hedef qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Eşdeğer:

```qsharp
Controlled Z([control], target);
```