---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: Integerbits işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855412"
---
# <a name="integerbits-function"></a>Integerbits işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Örnek

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```