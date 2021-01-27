---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: Bigenyen Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843386"
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