---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 1ce83389f2ac3ce9ab2898f9d167941ca2973508
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834606"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="8bc3b-102">BigIntAsBoolArray işlevi</span><span class="sxs-lookup"><span data-stu-id="8bc3b-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="8bc3b-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="8bc3b-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="8bc3b-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8bc3b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8bc3b-105">Verilen büyük tamsayıyı bir Boole dizisine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="8bc3b-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="8bc3b-106">Dizinin 0 öğesi, büyük tamsayının en az önemli bitidir.</span><span class="sxs-lookup"><span data-stu-id="8bc3b-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="8bc3b-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="8bc3b-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="8bc3b-108">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8bc3b-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="8bc3b-109">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="8bc3b-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="8bc3b-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="8bc3b-110">Remarks</span></span>

<span data-ttu-id="8bc3b-111">Daha fazla bilgi için bkz. [C# BigInteger Oluşturucusu](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="8bc3b-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>