---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728639"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


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