---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: Phaselitttaendian Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730591"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="d9879-102">Phaselitttaendian Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="d9879-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="d9879-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d9879-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d9879-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9879-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9879-105">QFT 'de küçük endian işaretsiz tamsayılar.</span><span class="sxs-lookup"><span data-stu-id="d9879-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="d9879-106">Örneğin, $ \ket{x} $, hesaplama tabanında $x $ tamsayının küçük endian kodusıdır $ \operatorname{QFTLE} \ket{x} $, QFT 'de $x $ kodlaması örneğidir.</span><span class="sxs-lookup"><span data-stu-id="d9879-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="d9879-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d9879-107">Remarks</span></span>

<span data-ttu-id="d9879-108">`PhaseLittleEndian`Belgelerde olduğu gibi kısaldık `PhaseLE` .</span><span class="sxs-lookup"><span data-stu-id="d9879-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9879-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d9879-109">See Also</span></span>

- [<span data-ttu-id="d9879-110">Microsoft. hisse. Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="d9879-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="d9879-111">Microsoft. hisse. Canon. QFTLE</span><span class="sxs-lookup"><span data-stu-id="d9879-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)