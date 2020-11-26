---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Sizeayarlantedtruthtable işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202932"
---
# <a name="sizeadjustedtruthtable-function"></a>Sizeayarlantedtruthtable işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Değer sayısına göre, bir dizi Boole değerinden Truth tablosunu ayarlar

Yeni bir dizi `2^numVars` , büyük olasılıkla, `table` `false` girdilerle veya öğelere kesilmek için gereken uzunluktadır `2^numVars` .

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Giriş

### <a name="table--bool"></a>Tablo: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Gerçeği değeri dizi olarak Truth tablosu


### <a name="numvars--int"></a>numVars: [Int](xref:microsoft.quantum.lang-ref.int)

Değişken sayısı



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Boyut ayarlanan Truth tablosu