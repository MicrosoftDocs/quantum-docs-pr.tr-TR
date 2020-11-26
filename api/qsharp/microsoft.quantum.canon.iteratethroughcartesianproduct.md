---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: 6340c7a972253e6f583a3856df93a7066ced3139
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206452"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Birkaç aralığın Kartezyen üründeki her bir dizin için bir işlem uygular.

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Açıklama

Yinelemeli olarak,,, `0..(bounds[0] - 1)` `0..(bounds[1] - 1)` ,..., Kartezyen ürünün her bir öğesi için bir işlem uygular `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>Giriş

### <a name="bounds--int"></a>sınırlar: [Int](xref:microsoft.quantum.lang-ref.int)[]

Her Aralık bir tamsayı uzunluğu olarak belirtilmekte olan, tekrarlandırılacak aralıkları belirten bir dizi.


### <a name="op--int--unit"></a>Op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Verilen Kartezyen ürünün her öğesi için çağrılacak bir işlem.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)