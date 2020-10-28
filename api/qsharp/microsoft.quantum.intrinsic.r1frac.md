---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731370"
---
# <a name="r1frac-operation"></a>R1Frac işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Leyebilir [](https://nuget.org/packages/)


$ \Ket {1} $ durumu ile dyadic kesri olarak belirtilen bir açıda bir döndürme uygular.

\begin{hizalaması} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {ı \ Pi k/2 ^ n}).
\end{hizalaması}

> [!WARNING]
> Bu işlem, öğesinden **ters** oturum açma kuralını kullanır @"microsoft.quantum.intrinsic.r" ve tarafından dahil edilen $1/2 $ faktörünü içermez @"microsoft.quantum.intrinsic.r1" .

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>Giriş

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
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```