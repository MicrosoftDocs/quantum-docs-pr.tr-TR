---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 127f2e51e19c76f4f7973bf1ac2217d4fffd72f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848367"
---
# <a name="expmodl-function"></a>ExpModL işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir mod için verilen bir kuvvete verilen bir tamsayıyı döndürür.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Description

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