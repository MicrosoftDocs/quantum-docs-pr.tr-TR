---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814394"
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