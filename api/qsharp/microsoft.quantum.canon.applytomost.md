---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: Applytoen işlem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850600"
---
# <a name="applytomost-operation"></a>Applytoen işlem

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir dizinin son öğesine, ancak sonuna uygular.

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Description

Bir işlem `op` ve bir hedef dizisi verildiğinde `targets` , geçerlidir `op(Most(targets))` .

## <a name="input"></a>Giriş

### <a name="op--t--unit"></a>Op: 'T [] => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Uygulanacak bir işlem.


### <a name="targets--t"></a>hedefler: 'T []

Bir dizi hedefi, ancak sonuncusu en son uygulanacak `op` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Uygulanacak işlemin giriş türü.

## <a name="example"></a>Örnek

Aşağıdaki Q # parçacıkları eşdeğerdir:

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. hisse. Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Microsoft. hisse. Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)