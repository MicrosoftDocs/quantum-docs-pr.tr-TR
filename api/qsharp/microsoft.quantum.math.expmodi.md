---
uid: Microsoft.Quantum.Math.ExpModI
title: Expmodı işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857044"
---
# <a name="expmodi-function"></a>Expmodı işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir mod için verilen bir kuvvete verilen bir tamsayıyı döndürür.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Description

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