---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Phaselitttaendian Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730591"
---
# <a name="phaselittleendian-user-defined-type"></a>Phaselitttaendian Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


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