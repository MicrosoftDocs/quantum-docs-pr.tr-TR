---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210769"
---
# <a name="expmodl-function"></a><span data-ttu-id="fa8da-102">ExpModL işlevi</span><span class="sxs-lookup"><span data-stu-id="fa8da-102">ExpModL function</span></span>

<span data-ttu-id="fa8da-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fa8da-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fa8da-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa8da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa8da-105">Belirli bir mod için verilen bir kuvvete verilen bir tamsayıyı döndürür.</span><span class="sxs-lookup"><span data-stu-id="fa8da-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="fa8da-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fa8da-106">Description</span></span>

<span data-ttu-id="fa8da-107">$X $, Power by $p $ ve mod $N $ ile karşılaştırarak expBase 'i belirlememize izin verin.</span><span class="sxs-lookup"><span data-stu-id="fa8da-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="fa8da-108">İşlev, $x ^ p \operatorname{mod} N $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="fa8da-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="fa8da-109">$N $, $x $ öğesinin olumlu ve gücün negatif olmadığı varsayılır.</span><span class="sxs-lookup"><span data-stu-id="fa8da-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="fa8da-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="fa8da-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="fa8da-111">expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fa8da-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="fa8da-112">güç: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fa8da-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="fa8da-113">mod: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fa8da-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="fa8da-114">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fa8da-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="fa8da-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fa8da-115">Remarks</span></span>

<span data-ttu-id="fa8da-116">, İçinde değil, içindeki bit sayısıyla orantılı bir zaman alır `power` `power` .</span><span class="sxs-lookup"><span data-stu-id="fa8da-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>