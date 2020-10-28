---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: Litttaendian Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731466"
---
# <a name="littleendian-user-defined-type"></a>Litttaendian Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


İşaretsiz bir tamsayıyı küçük endian düzeninde kodlayan kayıt. Index ile qubit, `0` işaretsiz bir tamsayının en düşük bitini kodluyor.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Açıklamalar

`LittleEndian`Belgelerde olduğu gibi kısaldık `LE` .