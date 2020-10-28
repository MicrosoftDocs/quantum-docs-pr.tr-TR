---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728645"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


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