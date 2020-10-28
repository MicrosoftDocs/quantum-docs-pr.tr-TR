---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Integerbits işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730666"
---
# <a name="integerbits-function"></a>Integerbits işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Leyebilir [](https://nuget.org/packages/)


Tamsayının bit sayısının ayarlandığı tüm pozisyonları döndürür.

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>Giriş

### <a name="value--int"></a>değer: [Int](xref:microsoft.quantum.lang-ref.int)

Negatif olmayan bir sayı.


### <a name="length--int"></a>Uzunluk: [Int](xref:microsoft.quantum.lang-ref.int)

İkili genişletmesinde bit sayısı `value` .



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

`value`Tüm bitleri konuma kadar ele almak için ikili genişlemesinde 1 olan tüm bit konumlarını (0 ' dan başlayarak) içeren bir dizi `length - 1` .  Tüm pozisyonlar, dizi içinde artan bir düzende konuma göre sıralanır.