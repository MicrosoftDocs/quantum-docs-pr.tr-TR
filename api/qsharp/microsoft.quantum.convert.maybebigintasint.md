---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: d0a598497e8a8f019bbd8da7db1c6cc4d7bde017
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224284"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="c8219-102">MaybeBigIntAsInt işlevi</span><span class="sxs-lookup"><span data-stu-id="c8219-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="c8219-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="c8219-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="c8219-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="c8219-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="c8219-105">Mümkünse, verilen büyük tamsayıyı eşdeğer tamsayıya dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="c8219-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="c8219-106">İşlevi, sonuç tamsayısı ve yalnızca dönüştürme mümkün olduğunda true olan bir Boolean bayrağının çiftini döndürür.</span><span class="sxs-lookup"><span data-stu-id="c8219-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="c8219-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="c8219-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c8219-108">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8219-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="c8219-109">Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool))</span><span class="sxs-lookup"><span data-stu-id="c8219-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="c8219-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c8219-110">Remarks</span></span>

<span data-ttu-id="c8219-111">Daha fazla bilgi için bkz. [C# BigInteger Oluşturucusu](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="c8219-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>