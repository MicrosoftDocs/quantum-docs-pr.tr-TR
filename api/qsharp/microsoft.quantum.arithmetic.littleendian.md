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
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="c5a4e-102">Litttaendian Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="c5a4e-102">LittleEndian user defined type</span></span>

<span data-ttu-id="c5a4e-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c5a4e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c5a4e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5a4e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5a4e-105">İşaretsiz bir tamsayıyı küçük endian düzeninde kodlayan kayıt.</span><span class="sxs-lookup"><span data-stu-id="c5a4e-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="c5a4e-106">Index ile qubit, `0` işaretsiz bir tamsayının en düşük bitini kodluyor.</span><span class="sxs-lookup"><span data-stu-id="c5a4e-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="c5a4e-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c5a4e-107">Remarks</span></span>

<span data-ttu-id="c5a4e-108">`LittleEndian`Belgelerde olduğu gibi kısaldık `LE` .</span><span class="sxs-lookup"><span data-stu-id="c5a4e-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>