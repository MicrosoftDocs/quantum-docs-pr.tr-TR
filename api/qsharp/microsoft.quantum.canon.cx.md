---
uid: Microsoft.Quantum.Canon.CX
title: CX işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: e27b30a6b4609daaac2cc5eda68120115777af0c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840749"
---
# <a name="cx-operation"></a>CX işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Denetlenen X (CX) kapısını bir qubit çiftiyle uygular.

$ $ \begin{hizalaması} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{hizalaması}, $ $ burada satırlar ve sütunlar hisse kavramları kılavuzunda olduğu gibi düzenlenmiştir.

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="control--qubit"></a>Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)

CX kapısı için denetim qubit.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

CX kapısı için hedef qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Eşdeğer:

```qsharp
Controlled X([control], target);
```

ve için:

```qsharp
CNOT(control, target);
```