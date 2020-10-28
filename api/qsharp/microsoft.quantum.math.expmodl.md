---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733063"
---
# <a name="expmodl-function"></a>ExpModL işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


Belirli bir mod için verilen bir kuvvete verilen bir tamsayıyı döndürür.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Açıklama

$X $, Power by $p $ ve mod $N $ ile karşılaştırarak expBase 'i belirlememize izin verin.
İşlev, $x ^ p \operatorname{mod} N $ döndürür.

$N $, $x $ öğesinin olumlu ve gücün negatif olmadığı varsayılır.

## <a name="input"></a>Giriş

### <a name="expbase--bigint"></a>expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>güç: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>mod: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Açıklamalar

, İçinde değil, içindeki bit sayısıyla orantılı bir zaman alır `power` `power` .