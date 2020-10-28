---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Sizeayarlantedtruthtable işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734058"
---
# <a name="sizeadjustedtruthtable-function"></a>Sizeayarlantedtruthtable işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Leyebilir [](https://nuget.org/packages/)


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