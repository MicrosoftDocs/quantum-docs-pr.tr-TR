---
uid: Microsoft.Quantum.Math.BigFraction
title: Bigkesir Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732767"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="c7a64-102">Bigkesir Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="c7a64-102">BigFraction user defined type</span></span>

<span data-ttu-id="c7a64-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c7a64-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c7a64-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c7a64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c7a64-105">Formun bir Rational numarasını temsil eder `p/q` .</span><span class="sxs-lookup"><span data-stu-id="c7a64-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="c7a64-106">Tamsayı, `p` kayıt düzeninin ilk öğesidir ve `q` kayıt düzeninin ikinci öğesidir.</span><span class="sxs-lookup"><span data-stu-id="c7a64-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="c7a64-107">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="c7a64-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="c7a64-108">Pay: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c7a64-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c7a64-109">Kesirin pay değeri.</span><span class="sxs-lookup"><span data-stu-id="c7a64-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="c7a64-110">Payda: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c7a64-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c7a64-111">Kesir paydası/</span><span class="sxs-lookup"><span data-stu-id="c7a64-111">Denominator of the fraction/</span></span>