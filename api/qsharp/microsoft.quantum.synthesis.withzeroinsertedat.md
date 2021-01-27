---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Withsıfırlaması ınsertedat işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855208"
---
# <a name="withzeroinsertedat-function"></a>Withsıfırlaması ınsertedat işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tamsayıya 0 bit ekleyin

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a>Description

Bu işlem bir tamsayı alır, bit olarak 0 ekler `position` ve güncelleştirilmiş değeri bir tamsayı olarak döndürür.  Örneğin, saat 2 ' de 2 ' ye (10 $ {10} $ = 1010_ {2} $) 0 eklemek 18 ($18 _ = {10} 10010_ $) sayısını döndürür {2} .

## <a name="input"></a>Giriş

### <a name="position--int"></a>Konum: [Int](xref:microsoft.quantum.lang-ref.int)

0 ' ın eklendiği konum


### <a name="value--int"></a>değer: [Int](xref:microsoft.quantum.lang-ref.int)

Değiştirilen değer



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Değiştirilen değer