---
uid: Microsoft.Quantum.Arrays.Chunks
title: Öbekleri işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221615"
---
# <a name="chunks-function"></a>Öbekleri işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir diziyi eşit uzunlukta birden çok parçaya böler.

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Giriş

### <a name="nelements--int"></a>nElements: [Int](xref:microsoft.quantum.lang-ref.int)

Her bir öbekin uzunluğu.


### <a name="arr--t"></a>ARR: 'T []

Bölünecek dizi.



## <a name="output--t"></a>Çıkış: 'T [] []

Özgün dizinin her öbeğini içeren bir dizi.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

Çıktının son öğesi `nElements` `Length(arr)` tarafından bölünemediğinden daha kısa olabileceğini unutmayın `nElements` .