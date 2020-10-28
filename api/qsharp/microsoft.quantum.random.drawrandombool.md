---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730954"
---
# <a name="drawrandombool-operation"></a>DrawRandomBool işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Leyebilir [](https://nuget.org/packages/)


Başarılı bir olasılık verildiğinde, verilen olasılığa sahip tek bir Bernoulli denemesi döndürür.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Giriş

### <a name="successprobability--double"></a>Başarılı olasılık: [Double](xref:microsoft.quantum.lang-ref.double)

`true`Döndürülecek olasılık.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` olasılık `successProbability` ve `false` olasılık `1.0 - successProbability` .