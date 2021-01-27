---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 127f2e51e19c76f4f7973bf1ac2217d4fffd72f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848367"
---
# <a name="expmodl-function"></a><span data-ttu-id="d44db-102">ExpModL işlevi</span><span class="sxs-lookup"><span data-stu-id="d44db-102">ExpModL function</span></span>

<span data-ttu-id="d44db-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="d44db-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="d44db-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d44db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d44db-105">Belirli bir mod için verilen bir kuvvete verilen bir tamsayıyı döndürür.</span><span class="sxs-lookup"><span data-stu-id="d44db-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="d44db-106">Description</span><span class="sxs-lookup"><span data-stu-id="d44db-106">Description</span></span>

<span data-ttu-id="d44db-107">$X $, Power by $p $ ve mod $N $ ile karşılaştırarak expBase 'i belirlememize izin verin.</span><span class="sxs-lookup"><span data-stu-id="d44db-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="d44db-108">İşlev, $x ^ p \operatorname{mod} N $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="d44db-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="d44db-109">$N $, $x $ öğesinin olumlu ve gücün negatif olmadığı varsayılır.</span><span class="sxs-lookup"><span data-stu-id="d44db-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="d44db-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="d44db-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="d44db-111">expBase: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d44db-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="d44db-112">güç: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d44db-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="d44db-113">mod: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d44db-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="d44db-114">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d44db-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="d44db-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d44db-115">Remarks</span></span>

<span data-ttu-id="d44db-116">, İçinde değil, içindeki bit sayısıyla orantılı bir zaman alır `power` `power` .</span><span class="sxs-lookup"><span data-stu-id="d44db-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>