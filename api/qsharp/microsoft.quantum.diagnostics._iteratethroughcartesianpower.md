---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: a27302be75ee701b0629310700b56d222aaef7db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853575"
---
# <a name="_iteratethroughcartesianpower-operation"></a>_iterateThroughCartesianPower işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Bir değeri Kartezyen ürün [0, sınır [0]-1] × [0, sınır [1]-1] × [0, sınır [Uzunluk (sınır)-1]-1] ve Kartezyen ürünün her öğesi için op (ARR) çağrısı

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>Giriş

### <a name="length--int"></a>Uzunluk: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>değer: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>Op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

