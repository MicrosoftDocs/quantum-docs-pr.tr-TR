---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846216"
---
# <a name="drawmany-operation"></a>DrawMany işlemi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi belirli sayıda örnek için yineler ve çıktılarını bir dizide toplar.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Giriş

### <a name="op--tinput--toutput"></a>Op: ' TInput => ' TOutput 

İşlemin tekrar çağrılması.


### <a name="nsamples--int"></a>nSamples: [Int](xref:microsoft.quantum.lang-ref.int)

Toplanacak çağrı örnekleri sayısı `op` .


### <a name="input--tinput"></a>Giriş: ' TInput

Geçirilecek giriş `op` .



## <a name="output--toutput"></a>Çıkış: ' TOutput []



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="tinput"></a>' TInput


### <a name="toutput"></a>' TOutput



## <a name="example"></a>Örnek

Aşağıdaki örnek, bir kerede tek bir bit örneklerindeki bir işlem verildiğinde bir tamsayıdır.

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)