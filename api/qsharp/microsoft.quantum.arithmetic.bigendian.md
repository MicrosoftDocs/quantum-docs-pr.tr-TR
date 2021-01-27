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
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="b3947-102">Bigenyen Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="b3947-102">BigEndian user defined type</span></span>

<span data-ttu-id="b3947-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b3947-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b3947-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b3947-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b3947-105">İşaretsiz bir tamsayıyı büyük endian düzeninde kodlayan kayıt.</span><span class="sxs-lookup"><span data-stu-id="b3947-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="b3947-106">Index ile qubit, `0` işaretsiz bir tamsayının en yüksek bitini kodluyor.</span><span class="sxs-lookup"><span data-stu-id="b3947-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="b3947-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b3947-107">Remarks</span></span>

<span data-ttu-id="b3947-108">`BigEndian`Belgelerde olduğu gibi kısaldık `BE` .</span><span class="sxs-lookup"><span data-stu-id="b3947-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>