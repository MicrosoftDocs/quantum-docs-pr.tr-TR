---
uid: Microsoft.Quantum.Math.ExpModI
title: Expmodı işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857044"
---
# <a name="expmodi-function"></a><span data-ttu-id="59935-102">Expmodı işlevi</span><span class="sxs-lookup"><span data-stu-id="59935-102">ExpModI function</span></span>

<span data-ttu-id="59935-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="59935-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="59935-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59935-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59935-105">Belirli bir mod için verilen bir kuvvete verilen bir tamsayıyı döndürür.</span><span class="sxs-lookup"><span data-stu-id="59935-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="59935-106">Description</span><span class="sxs-lookup"><span data-stu-id="59935-106">Description</span></span>

<span data-ttu-id="59935-107">$X $, Power by $p $ ve mod $N $ ile karşılaştırarak expBase 'i belirlememize izin verin.</span><span class="sxs-lookup"><span data-stu-id="59935-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="59935-108">İşlev, $x ^ p \operatorname{mod} N $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="59935-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="59935-109">$N $, $x $ öğesinin olumlu ve gücün negatif olmadığı varsayılır.</span><span class="sxs-lookup"><span data-stu-id="59935-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="59935-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="59935-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="59935-111">expBase: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59935-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="59935-112">güç: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59935-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="59935-113">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59935-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="59935-114">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="59935-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="59935-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="59935-115">Remarks</span></span>

<span data-ttu-id="59935-116">, İçinde değil, içindeki bit sayısıyla orantılı bir zaman alır `power` `power` .</span><span class="sxs-lookup"><span data-stu-id="59935-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>