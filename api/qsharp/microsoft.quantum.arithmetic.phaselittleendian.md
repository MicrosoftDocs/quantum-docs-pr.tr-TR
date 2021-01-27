---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Phaselitttaendian Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842995"
---
# <a name="phaselittleendian-user-defined-type"></a>Phaselitttaendian Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


QFT 'de küçük endian işaretsiz tamsayılar.

Örneğin, $ \ket{x} $, hesaplama tabanında $x $ tamsayının küçük endian kodusıdır $ \operatorname{QFTLE} \ket{x} $, QFT 'de $x $ kodlaması örneğidir.

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Açıklamalar

`PhaseLittleEndian`Belgelerde olduğu gibi kısaldık `PhaseLE` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Microsoft. hisse. Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)