---
uid: Microsoft.Quantum.Intrinsic.Rz
title: RZ işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: d637abf3562eb60705da517467939dc588229c39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198631"
---
# <a name="rz-operation"></a>RZ işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


$Z $-ekseni ile verilen bir açıda bir döndürme uygular.

\begin{hizalaması} R_z (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \teta/2} & 0 \\ \\ 0 & e ^ {ı \ teta/2} \end{bmatrix}.
\end{hizalaması}

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="theta--double"></a>Teta: [Double](xref:microsoft.quantum.lang-ref.double)

Qubitin döndürüleceği açı.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Gate 'in uygulanması gereken qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Eşdeğer:

```qsharp
R(PauliZ, theta, qubit);
```