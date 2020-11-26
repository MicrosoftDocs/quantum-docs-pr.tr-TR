---
uid: Microsoft.Quantum.Intrinsic.R
title: R işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199038"
---
# <a name="r-operation"></a>R işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Verilen Pauli ekseni hakkında bir döndürme uygular.

\begin{hizalaması} R_ {\mu} (\teta) \mathrel{: =} e ^ {-i \teta \ sigma_ {\mu}/2}, \end{hizalaması}; burada $ \mu \ in \{ i, X, Y, Z \} $.

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Dönüşü oluşturmak için Pauli işleci ($ \mu $) üs olarak dağıtılır.


### <a name="theta--double"></a>Teta: [Double](xref:microsoft.quantum.lang-ref.double)

Qubitin döndürüleceği açı.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Gate 'in uygulanması gereken qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

İle çağrıldığında `pauli = PauliI` , bu işlem *genel bir aşama* uygular. Bu aşama, functor ile kullanıldığında önemli olabilir `Controlled` .