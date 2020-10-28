---
uid: Microsoft.Quantum.Math.ExpModI
title: Expmodı işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732855"
---
# <a name="expmodi-function"></a><span data-ttu-id="4d93a-102">Expmodı işlevi</span><span class="sxs-lookup"><span data-stu-id="4d93a-102">ExpModI function</span></span>

<span data-ttu-id="4d93a-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4d93a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4d93a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d93a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d93a-105">Belirli bir mod için verilen bir kuvvete verilen bir tamsayıyı döndürür.</span><span class="sxs-lookup"><span data-stu-id="4d93a-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="4d93a-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4d93a-106">Description</span></span>

<span data-ttu-id="4d93a-107">$X $, Power by $p $ ve mod $N $ ile karşılaştırarak expBase 'i belirlememize izin verin.</span><span class="sxs-lookup"><span data-stu-id="4d93a-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="4d93a-108">İşlev, $x ^ p \operatorname{mod} N $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="4d93a-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="4d93a-109">$N $, $x $ öğesinin olumlu ve gücün negatif olmadığı varsayılır.</span><span class="sxs-lookup"><span data-stu-id="4d93a-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="4d93a-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="4d93a-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="4d93a-111">expBase: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d93a-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="4d93a-112">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d93a-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="4d93a-113">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d93a-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="4d93a-114">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4d93a-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="4d93a-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4d93a-115">Remarks</span></span>

<span data-ttu-id="4d93a-116">, İçinde değil, içindeki bit sayısıyla orantılı bir zaman alır `power` `power` .</span><span class="sxs-lookup"><span data-stu-id="4d93a-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>