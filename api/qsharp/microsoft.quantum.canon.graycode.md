---
uid: Microsoft.Quantum.Canon.GrayCode
title: Gricode işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728699"
---
# <a name="graycode-function"></a>Gricode işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Gri kod sıraları oluşturur

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Giriş

### <a name="n--int"></a>n: [Int](xref:microsoft.quantum.lang-ref.int)

Bit sayısı



## <a name="output--intint"></a>Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Tanımlama grubu dizisi. Kayıt alanındaki ilk değer, bir sonraki bir değere ulaşmak için geçerli değerde değişmek üzere, kayıt düzeni içindeki Ikinci değer olan gride bir değerdir.