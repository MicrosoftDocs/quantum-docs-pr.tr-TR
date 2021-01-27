---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840273"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Birkaç aralığın Kartezyen üründeki her bir dizin için bir işlem uygular.

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Description

Yinelemeli olarak,,, `0..(bounds[0] - 1)` `0..(bounds[1] - 1)` ,..., Kartezyen ürünün her bir öğesi için bir işlem uygular `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>Giriş

### <a name="bounds--int"></a>sınırlar: [Int](xref:microsoft.quantum.lang-ref.int)[]

Her Aralık bir tamsayı uzunluğu olarak belirtilmekte olan, tekrarlandırılacak aralıkları belirten bir dizi.


### <a name="op--int--unit"></a>Op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Verilen Kartezyen ürünün her öğesi için çağrılacak bir işlem.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

Bir işlem verildiğinde `op` , aşağıdaki iki kod parçacığı eşdeğerdir:

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)