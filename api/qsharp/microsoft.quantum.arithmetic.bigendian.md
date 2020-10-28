---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: Bigenyen Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731674"
---
# <a name="bigendian-user-defined-type"></a>Bigenyen Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


İşaretsiz bir tamsayıyı büyük endian düzeninde kodlayan kayıt. Index ile qubit, `0` işaretsiz bir tamsayının en yüksek bitini kodluyor.

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>Açıklamalar

`BigEndian`Belgelerde olduğu gibi kısaldık `BE` .