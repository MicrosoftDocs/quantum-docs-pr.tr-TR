---
uid: Microsoft.Quantum.Math.ExpModI
title: Expmodı işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732855"
---
# <a name="expmodi-function"></a>Expmodı işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


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