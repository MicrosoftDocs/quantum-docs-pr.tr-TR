---
uid: Microsoft.Quantum.Math.ExpModI
title: Expmodı işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228500"
---
# <a name="expmodi-function"></a>Expmodı işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir mod için verilen bir kuvvete verilen bir tamsayıyı döndürür.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Açıklama

$X $, Power by $p $ ve mod $N $ ile karşılaştırarak expBase 'i belirlememize izin verin.
İşlev, $x ^ p \operatorname{mod} N $ döndürür.

$N $, $x $ öğesinin olumlu ve gücün negatif olmadığı varsayılır.

## <a name="input"></a>Giriş

### <a name="expbase--int"></a>expBase: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>güç: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>mod: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>Açıklamalar

, İçinde değil, içindeki bit sayısıyla orantılı bir zaman alır `power` `power` .