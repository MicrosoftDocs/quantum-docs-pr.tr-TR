---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: Bigenyen Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223672"
---
# <a name="bigendian-user-defined-type"></a>Bigenyen Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İşaretsiz bir tamsayıyı büyük endian düzeninde kodlayan kayıt. Index ile qubit, `0` işaretsiz bir tamsayının en yüksek bitini kodluyor.

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>Açıklamalar

`BigEndian`Belgelerde olduğu gibi kısaldık `BE` .