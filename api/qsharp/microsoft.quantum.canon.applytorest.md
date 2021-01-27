---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850504"
---
# <a name="applytorest-operation"></a>ApplyToRest işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi, bir dizinin ilk öğesi hariç tümüne uygular.

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Description

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Rest(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit"></a>Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

Birincisi, ancak ilki uygulanacak bir dizi hedefi `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="example"></a>Örnek

Aşağıdaki Q # parçacıkları eşdeğerdir:

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToRestA](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [Microsoft. hisse. Canon. ApplyToRestC](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [Microsoft. hisse. Canon. ApplyToRestCA](xref:Microsoft.Quantum.Canon.ApplyToRestCA)