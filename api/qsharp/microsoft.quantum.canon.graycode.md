---
uid: Microsoft.Quantum.Canon.GrayCode
title: Gricode işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206893"
---
# <a name="graycode-function"></a>Gricode işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Gri kod sıraları oluşturur

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Giriş

### <a name="n--int"></a>n: [Int](xref:microsoft.quantum.lang-ref.int)

Bit sayısı



## <a name="output--intint"></a>Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Tanımlama grubu dizisi. Kayıt alanındaki ilk değer, bir sonraki bir değere ulaşmak için geçerli değerde değişmek üzere, kayıt düzeni içindeki Ikinci değer olan gride bir değerdir.