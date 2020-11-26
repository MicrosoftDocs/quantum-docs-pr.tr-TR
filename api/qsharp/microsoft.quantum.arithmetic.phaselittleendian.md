---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Phaselitttaendian Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222431"
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