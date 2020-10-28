---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732938"
---
# <a name="rfrac-operation"></a>RFrac işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Leyebilir [](https://nuget.org/packages/)


Verilen Pauli ekseni ile dyadic kesri olarak belirtilen bir açıda bir döndürme uygular.

\begin{hizalaması} R_ {\mu} (n, k) \mathrel{: =} e ^ {ı \pi n \ sigma_ {\mu}/2 ^ k}, \end{hizalaması}; burada $ \mu \ in \{ i, X, Y, Z \} $.

> [!WARNING]
> Bu işlem, öğesinden **ters** oturum açma kuralını kullanır @"microsoft.quantum.intrinsic.r" .

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>Giriş

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Dönüşü oluşturmak için üs olacak Pauli işleci.


### <a name="numerator--int"></a>pay: [Int](xref:microsoft.quantum.lang-ref.int)

Dyadic kesir gösteriminde, qubitin döndürüleceği açının değeri.


### <a name="power--int"></a>güç: [Int](xref:microsoft.quantum.lang-ref.int)

İkinin, qubitin döndürüleceği açının paydasını belirten iki üssü.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Gate 'in uygulanması gereken qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Eşdeğer:

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```