---
uid: Microsoft.Quantum.Canon.GrayCode
title: Gricode işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840490"
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

## <a name="example"></a>Örnek

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```