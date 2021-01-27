---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853685"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Başarılı bir olasılık verildiğinde, verilen olasılığa sahip tek bir Bernoulli denemesi döndürür.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Giriş

### <a name="successprobability--double"></a>Başarılı olasılık: [Double](xref:microsoft.quantum.lang-ref.double)

`true`Döndürülecek olasılık.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` olasılık `successProbability` ve `false` olasılık `1.0 - successProbability` .

## <a name="example"></a>Örnek

Aşağıdaki Q # kod parçacığı örnekleri, taraflı bir para ile döndürülür:

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```