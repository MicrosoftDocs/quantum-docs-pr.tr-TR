---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 2883e7cb30633afe51d380befe806665207c5abd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206485"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tamsayı aralığının Kartezyen kuvveti içindeki her dizin için bir işlem uygular.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Açıklama

Yinelemeli olarak, aralığın Kartezyen her öğesi için bir işlem uygular `0..(bound - 1)` .

## <a name="input"></a>Giriş

### <a name="power--int"></a>güç: [Int](xref:microsoft.quantum.lang-ref.int)

Aralığın oluşturulması gereken Kartezyen güç `0..(bound - 1)` .


### <a name="bound--int"></a>bağlıydı: [Int](xref:microsoft.quantum.lang-ref.int)

Aralığın uzunluğu olarak belirtilen, tekrarlandırılmış aralığın bir belirtimi.


### <a name="op--int--unit"></a>Op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Verilen Kartezyen her öğe için çağrılacak bir işlem.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)