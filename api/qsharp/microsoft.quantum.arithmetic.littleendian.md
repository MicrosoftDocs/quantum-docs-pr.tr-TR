---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: Litttaendian Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846559"
---
# <a name="littleendian-user-defined-type"></a>Litttaendian Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İşaretsiz bir tamsayıyı küçük endian düzeninde kodlayan kayıt. Index ile qubit, `0` işaretsiz bir tamsayının en düşük bitini kodluyor.

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Açıklamalar

`LittleEndian`Belgelerde olduğu gibi kısaldık `LE` .