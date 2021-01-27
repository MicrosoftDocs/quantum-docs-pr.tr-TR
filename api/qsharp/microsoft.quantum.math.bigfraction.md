---
uid: Microsoft.Quantum.Math.BigFraction
title: Bigkesir Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846910"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="7fcc4-102">Bigkesir Kullanıcı tanımlı türü</span><span class="sxs-lookup"><span data-stu-id="7fcc4-102">BigFraction user defined type</span></span>

<span data-ttu-id="7fcc4-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="7fcc4-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="7fcc4-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7fcc4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7fcc4-105">Formun bir Rational numarasını temsil eder `p/q` .</span><span class="sxs-lookup"><span data-stu-id="7fcc4-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="7fcc4-106">Tamsayı, `p` kayıt düzeninin ilk öğesidir ve `q` kayıt düzeninin ikinci öğesidir.</span><span class="sxs-lookup"><span data-stu-id="7fcc4-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="7fcc4-107">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="7fcc4-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="7fcc4-108">Pay: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7fcc4-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7fcc4-109">Kesirin pay değeri.</span><span class="sxs-lookup"><span data-stu-id="7fcc4-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="7fcc4-110">Payda: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="7fcc4-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="7fcc4-111">Kesir paydası/</span><span class="sxs-lookup"><span data-stu-id="7fcc4-111">Denominator of the fraction/</span></span>