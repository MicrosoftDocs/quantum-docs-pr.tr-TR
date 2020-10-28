---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730351"
---
# <a name="drawmany-operation"></a>DrawMany işlemi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Repeat](xref:Microsoft.Quantum.Canon.Repeat)