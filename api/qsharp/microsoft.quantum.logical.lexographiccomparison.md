---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726017"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Leyebilir [](https://nuget.org/packages/)


Bir karşılaştırma işlevi verildiğinde, sözcüografiksel olarak iki diziyi karşılaştıran yeni bir işlev döndürür.

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>Giriş

### <a name="elementcomparison--tt---bool"></a>elementComparison: ('T, 'T)-> [bool](xref:microsoft.quantum.lang-ref.bool)

İki öğeyi karşılaştıran ve `x` `y` ' `x` den küçük veya eşitse dönen bir işlev `y` .



## <a name="output--tt---bool"></a>Çıkış: ('T [], 'T [])-> [bool](xref:microsoft.quantum.lang-ref.bool)

İki diziyi karşılaştıran ve `xs` `ys` `xs` sözcüograf sıralamasına göre veya ona eşit olduğunda döndüren bir işlev `ys` .

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Karşılaştırılan dizilerin öğelerinin türü.

## <a name="remarks"></a>Açıklamalar

İki dizi arasındaki lexographic karşılaştırması `xs` ve `ys` Aşağıdaki yordam tarafından tanımlanmıştır. İki öğe olduğunu `x` ve `y` `elementComparison(x, y)` `elementComparison(y, x)` her ikisi de true olduğunu varsayalım.

- Her iki dizi de eşdeğer olmayan ilk öğe çifti kadar öğe öğesi ile karşılaştırılır. İlk olarak öğesine göre oluşan öğesini içeren dizi, `elementComparison` ilk olarak lexografik sıralaması içinde gerçekleştik.
- Herhangi bir kaçınması öğesi bulunmazsa ve bir dizi diğerinin daha uzunsa, daha kısa bir dizi ilk olarak ortaya çıkar.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. sıralanmış](xref:Microsoft.Quantum.Arrays.Sorted)