---
uid: Microsoft.Quantum.Canon.CY
title: CY işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 862f058e630ee6d9159e0fe514ca2dd1179ea9a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840728"
---
# <a name="cy-operation"></a>CY işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Denetimli-Y (CY) kapısını bir qubit çiftiyle uygular.

$ $ \begin{hizalaması} 1 & 0 & 0 & 0 0 \\ \\ & 1 & 0 & 0 0 & 0 & \\ \\ 0 &-ı 0 & 0 & \\ \\ ı & 0 \ End{hizalaması}, $ $ burada satır ve sütun, hisse kavramları kılavuzunda olduğu gibi düzenlenmiştir.

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="control--qubit"></a>Denetim: [qubit](xref:microsoft.quantum.lang-ref.qubit)

CY kapısı için qubit denetimi.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

CY kapısı için hedef qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Eşdeğer:

```qsharp
Controlled Y([control], target);
```