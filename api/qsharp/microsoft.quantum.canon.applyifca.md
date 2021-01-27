---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b9d5e2c6868dc7b876917abf28f68bb5d0d0f2f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844997"
---
# <a name="applyifca-operation"></a>ApplyIfCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik bir bit üzerinde bir Unitary işlemi uygular.

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bir işlem `op` ve bir bit değeri verildiğinde, `bit` if ise için geçerlidir `op` `target` `bit` `true` . Varsa, `false` hiçbir şey olmaz `target` .
Sonek, `CA` uygulanacak işlemin Unitary (denetlenebilir ve adjointable) olduğunu gösterir.

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj--ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Koşullu olarak uygulanacak bir işlem.


### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Op 'ın uygulanıp uygulanmadığını denetleyen bir Boole değeri.


### <a name="target--t"></a>Hedef: 'T

İşlemin uygulandığı giriş.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Koşullu olarak uygulanacak işlemin giriş türü.

## <a name="example"></a>Örnek

Aşağıdaki, bir qubits kaydını bir değer dizisi olarak verilen bir klasik bit dizesiyle temsil eden bir hesaplama tabanlı duruma hazırlar `Bool` :

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. hisse. Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. hisse. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)