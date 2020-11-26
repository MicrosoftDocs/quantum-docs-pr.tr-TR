---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228143"
---
# <a name="iscoprimel-function"></a>IsCoprimeL işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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