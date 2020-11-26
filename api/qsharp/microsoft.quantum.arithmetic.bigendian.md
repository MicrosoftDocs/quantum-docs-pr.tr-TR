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
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="c2c92-102">Bigenyen Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="c2c92-102">BigEndian user defined type</span></span>

<span data-ttu-id="c2c92-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c2c92-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c2c92-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2c92-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2c92-105">İşaretsiz bir tamsayıyı büyük endian düzeninde kodlayan kayıt.</span><span class="sxs-lookup"><span data-stu-id="c2c92-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="c2c92-106">Index ile qubit, `0` işaretsiz bir tamsayının en yüksek bitini kodluyor.</span><span class="sxs-lookup"><span data-stu-id="c2c92-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="c2c92-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c2c92-107">Remarks</span></span>

<span data-ttu-id="c2c92-108">`BigEndian`Belgelerde olduğu gibi kısaldık `BE` .</span><span class="sxs-lookup"><span data-stu-id="c2c92-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>