---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851338"
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