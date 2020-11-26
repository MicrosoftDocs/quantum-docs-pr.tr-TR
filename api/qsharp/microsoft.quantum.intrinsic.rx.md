---
uid: Microsoft.Quantum.Intrinsic.Rx
title: RX işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rx
qsharp.summary: >-
  Applies a rotation about the $x$-axis by a given angle.

  \begin{align} R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -i\sin \frac{\theta}{2}  \\\\ -i\sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 49638c00967ff2f47dad41acfed05868d65a24a0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198597"
---
# <a name="rx-operation"></a>RX işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


$X $-ekseni ile verilen bir açıda bir döndürme uygular.

\begin{hizalaması} R_x (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_x/2} = \begin{bmatrix} \cos \frac{\theta} {2} &-ı\sin \ FRAC{\theta}-i\sin \ FRAC{\theta} {2} \\ \\ {2} & \cos \ FRAC{\theta} {2} \end{bmatrix}.  
\end{hizalaması}

```qsharp
operation Rx (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
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
R(PauliX, theta, qubit);
```