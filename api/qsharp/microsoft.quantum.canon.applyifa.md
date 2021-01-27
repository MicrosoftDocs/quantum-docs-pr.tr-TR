---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 8bdca1bf286d564dfbb540bc9d63c035d2196f00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845033"
---
# <a name="applyifa-operation"></a>ApplyIfA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik bir bit üzerine koşullu bir adjointable işlemi uygular.

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a>Description

Bir işlem `op` ve bir bit değeri verildiğinde, `bit` if ise için geçerlidir `op` `target` `bit` `true` . Varsa, `false` hiçbir şey olmaz `target` .
Sonek, `A` uygulanacak işlemin adjointable olduğunu gösterir.

## <a name="input"></a>Giriş

### <a name="op--t--unit--is-adj"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı

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