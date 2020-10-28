---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Withsıfırlaması ınsertedat işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 6e13251741dadb19740b208cdfc13a14964a48dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733879"
---
# <a name="withzeroinsertedat-function"></a>Withsıfırlaması ınsertedat işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Leyebilir [](https://nuget.org/packages/)


Tamsayıya 0 bit ekleyin

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Açıklama

Bu işlem bir tamsayı alır, bit olarak 0 ekler `position` ve güncelleştirilmiş değeri bir tamsayı olarak döndürür.  Örneğin, saat 2 ' de 2 ' ye (10 $ {10} $ = 1010_ {2} $) 0 eklemek 18 ($18 _ = {10} 10010_ $) sayısını döndürür {2} .

## <a name="input"></a>Giriş

### <a name="position--int"></a>Konum: [Int](xref:microsoft.quantum.lang-ref.int)

0 ' ın eklendiği konum


### <a name="value--int"></a>değer: [Int](xref:microsoft.quantum.lang-ref.int)

Değiştirilen değer



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Değiştirilen değer