---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224471"
---
# <a name="boolarrayasresultarray-function"></a>BoolArrayAsResultArray işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir `Bool[]` türü `Result[]` türüne dönüştürür; burada `true` eşlenir ve ile `One` `false` eşlenir `Zero` .

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a>Giriş

### <a name="input--bool"></a>Giriş: [bool](xref:microsoft.quantum.lang-ref.bool)[]

`Bool[]` dönüştürülecek.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__[]

Öğesini `Result[]` temsil eden `input` .