---
uid: Microsoft.Quantum.Preparation.ApplyToLittleEndian
title: Applytolitttaendian işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApplyToLittleEndian
qsharp.summary: Applies an operation to the underlying qubits making up a little-endian register. This operation is marked as internal, as a little-endian register is intended to be "opaque," such that this is an implementation detail only.
ms.openlocfilehash: d94a9969a3f827d594946ab8ca6cd4672da7ef7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733279"
---
# <a name="applytolittleendian-operation"></a>Applytolitttaendian işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Leyebilir [](https://nuget.org/packages/)


Temel alınan qubits 'e bir işlem uygular ve bu da az endian bir kayıt yapar. Bu işlem iç olarak işaretlenir, çünkü küçük endian bir kayıt, yalnızca bir uygulama ayrıntısı olduğu gibi "donuk" olması amaçlanmıştır.

```qsharp
operation ApplyToLittleEndian (bareOp : (Qubit[] => Unit is Adj + Ctl), register : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Giriş

### <a name="bareop--qubit--unit-adj--ctl"></a>bareOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL




### <a name="register--littleendian"></a>kaydol: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

