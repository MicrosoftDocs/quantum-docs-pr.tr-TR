---
uid: Microsoft.Quantum.Intrinsic.Rz
title: RZ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731346"
---
# <a name="rz-operation"></a>RZ işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Leyebilir [](https://nuget.org/packages/)


$Z $-ekseni ile verilen bir açıda bir döndürme uygular.

\begin{hizalaması} R_z (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \teta/2} & 0 \\ \\ 0 & e ^ {ı \ teta/2} \end{bmatrix}.
\end{hizalaması}

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
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