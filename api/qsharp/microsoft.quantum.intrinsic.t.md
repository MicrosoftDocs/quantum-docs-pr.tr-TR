---
uid: Microsoft.Quantum.Intrinsic.T
title: T işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731338"
---
# <a name="t-operation"></a>T işlemi

Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)

Leyebilir [](https://nuget.org/packages/)


T geçidini tek bir qubit 'e uygular.

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a>Açıklama

Bu işlem, Unitary matrisi \ Begin{hizalaması} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {ı \ Pi/4} \end{bmatrix} tarafından benzetilir.
\end{hizalaması}

## <a name="input"></a>Giriş

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Gate 'in uygulanması gereken qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

