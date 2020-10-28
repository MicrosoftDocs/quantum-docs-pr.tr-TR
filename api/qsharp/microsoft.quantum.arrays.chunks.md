---
uid: Microsoft.Quantum.Arrays.Chunks
title: Öbekleri işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730415"
---
# <a name="chunks-function"></a>Öbekleri işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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