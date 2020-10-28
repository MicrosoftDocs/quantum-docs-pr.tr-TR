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
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="144c3-102">Bigenyen Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="144c3-102">BigEndian user defined type</span></span>

<span data-ttu-id="144c3-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="144c3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="144c3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="144c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="144c3-105">İşaretsiz bir tamsayıyı büyük endian düzeninde kodlayan kayıt.</span><span class="sxs-lookup"><span data-stu-id="144c3-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="144c3-106">Index ile qubit, `0` işaretsiz bir tamsayının en yüksek bitini kodluyor.</span><span class="sxs-lookup"><span data-stu-id="144c3-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="144c3-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="144c3-107">Remarks</span></span>

<span data-ttu-id="144c3-108">`BigEndian`Belgelerde olduğu gibi kısaldık `BE` .</span><span class="sxs-lookup"><span data-stu-id="144c3-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>