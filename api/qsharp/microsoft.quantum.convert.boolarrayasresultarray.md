---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834183"
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