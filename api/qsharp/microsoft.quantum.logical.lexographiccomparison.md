---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: 4d8596c52b0fc8082a2b766d95d4052a4964b8b9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197593"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison işlevi

Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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