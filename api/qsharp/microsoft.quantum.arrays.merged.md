---
uid: Microsoft.Quantum.Arrays.Merged
title: Birleştirilmiş işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730111"
---
# <a name="merged-function"></a>Birleştirilmiş işlev

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


İki sıralanmış dizi verildiğinde, her ikisi de sıralanmış düzende öğelerinin bulunduğu tek bir dizi döndürür. Birleştirme sıralaması tarafından dahili olarak kullanılır.

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>Giriş

### <a name="comparison--tt---bool"></a>Karşılaştırma: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>Sol: 'T []




### <a name="right--t"></a>Sağ: 'T []





## <a name="output--t"></a>Çıkış: 'T []



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

