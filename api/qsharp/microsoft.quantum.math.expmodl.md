---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733063"
---
# <a name="expmodl-function"></a><span data-ttu-id="88a1f-102">ExpModL işlevi</span><span class="sxs-lookup"><span data-stu-id="88a1f-102">ExpModL function</span></span>

<span data-ttu-id="88a1f-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="88a1f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="88a1f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="88a1f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="88a1f-105">Belirli bir mod için verilen bir kuvvete verilen bir tamsayıyı döndürür.</span><span class="sxs-lookup"><span data-stu-id="88a1f-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="88a1f-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="88a1f-106">Description</span></span>

<span data-ttu-id="88a1f-107">$X $, Power by $p $ ve mod $N $ ile karşılaştırarak expBase 'i belirlememize izin verin.</span><span class="sxs-lookup"><span data-stu-id="88a1f-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="88a1f-108">İşlev, $x ^ p \operatorname{mod} N $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="88a1f-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="88a1f-109">$N $, $x $ öğesinin olumlu ve gücün negatif olmadığı varsayılır.</span><span class="sxs-lookup"><span data-stu-id="88a1f-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="88a1f-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="88a1f-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="88a1f-111">expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="88a1f-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="88a1f-112">güç: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="88a1f-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="88a1f-113">mod: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="88a1f-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="88a1f-114">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="88a1f-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="88a1f-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="88a1f-115">Remarks</span></span>

<span data-ttu-id="88a1f-116">, İçinde değil, içindeki bit sayısıyla orantılı bir zaman alır `power` `power` .</span><span class="sxs-lookup"><span data-stu-id="88a1f-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>