---
uid: Microsoft.Quantum.Arrays.Chunks
title: Öbekleri işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842884"
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