---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Applytolitttaendian işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: a8c765d4b8f5d2f09cf68b7140e31c9114643733
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856986"
---
# <a name="applytolittleendian-operation"></a>Applytolitttaendian işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Temel alınan qubits 'e bir işlem uygular ve bu da az endian bir kayıt yapar. Bu işlem iç olarak işaretlenir, çünkü küçük endian bir kayıt, yalnızca bir uygulama ayrıntısı olduğu gibi "donuk" olması amaçlanmıştır.

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="bareop--qubit--unit--is-adj--ctl"></a>bareOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL




### <a name="register--littleendian"></a>kaydol: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

