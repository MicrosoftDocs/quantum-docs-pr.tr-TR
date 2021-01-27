---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833314"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="b1fe9-102">IntAsBoolArray işlevi</span><span class="sxs-lookup"><span data-stu-id="b1fe9-102">IntAsBoolArray function</span></span>

<span data-ttu-id="b1fe9-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="b1fe9-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="b1fe9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1fe9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1fe9-105">Döndürülen dizi için küçük endian gösterimini kullanarak negatif olmayan bir tamsayı için ikili bir temsilini üretir.</span><span class="sxs-lookup"><span data-stu-id="b1fe9-105">Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="b1fe9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b1fe9-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="b1fe9-107">Sayı: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1fe9-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1fe9-108">Boole değerleri dizisine dönüştürülecek negatif olmayan bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="b1fe9-108">A non-negative integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="b1fe9-109">bit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1fe9-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1fe9-110">Öğesinin ikili temsilindeki bit sayısı `number` .</span><span class="sxs-lookup"><span data-stu-id="b1fe9-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b1fe9-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="b1fe9-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="b1fe9-112">Temsil eden bir Boole değerleri dizisi `number` .</span><span class="sxs-lookup"><span data-stu-id="b1fe9-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1fe9-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b1fe9-113">Remarks</span></span>

<span data-ttu-id="b1fe9-114">Giriş `bits` 0 ile 63 arasında olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b1fe9-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="b1fe9-115">Giriş `number` 0 ile $2 ^ {\texttt{bits}}-$1 arasında olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="b1fe9-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>