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
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="5f9d0-102">Litttaendian Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="5f9d0-102">LittleEndian user defined type</span></span>

<span data-ttu-id="5f9d0-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5f9d0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5f9d0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5f9d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5f9d0-105">İşaretsiz bir tamsayıyı küçük endian düzeninde kodlayan kayıt.</span><span class="sxs-lookup"><span data-stu-id="5f9d0-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="5f9d0-106">Index ile qubit, `0` işaretsiz bir tamsayının en düşük bitini kodluyor.</span><span class="sxs-lookup"><span data-stu-id="5f9d0-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="5f9d0-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5f9d0-107">Remarks</span></span>

<span data-ttu-id="5f9d0-108">`LittleEndian`Belgelerde olduğu gibi kısaldık `LE` .</span><span class="sxs-lookup"><span data-stu-id="5f9d0-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>