---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732250"
---
# <a name="iscoprimel-function"></a>IsCoprimeL işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


$A $ ve $b $ ortak ana ise true, aksi takdirde false döndürür.

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Giriş

### <a name="a--bigint"></a>y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

ortak Prime 'nin test edilmekte olduğu ilk sayı


### <a name="b--bigint"></a>b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)

ortak Prime 'nin test edilmekte olan ikinci sayısı



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

$A $ ve $b $ ortak asal ise true (ör. en büyük ortak bölen 1), aksi takdirde false