---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: Sizeayarlantedtruthtable işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855314"
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