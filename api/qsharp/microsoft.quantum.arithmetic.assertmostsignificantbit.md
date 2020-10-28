---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731690"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="b6438-102">AssertMostSignificantBit işlemi</span><span class="sxs-lookup"><span data-stu-id="b6438-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="b6438-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b6438-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b6438-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6438-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6438-105">Bir qubit kayıt 'nın, işaretsiz bir tamsayıyı temsil eden en önemli qubitin belirli bir durumda olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="b6438-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b6438-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b6438-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="b6438-107">değer: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="b6438-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="b6438-108">Belirtilmekte olan en yüksek bit değeri.</span><span class="sxs-lookup"><span data-stu-id="b6438-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="b6438-109">Sayı: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b6438-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b6438-110">En yüksek bitin denetlenme işaretsiz tamsayı.</span><span class="sxs-lookup"><span data-stu-id="b6438-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6438-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6438-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b6438-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b6438-112">Remarks</span></span>

<span data-ttu-id="b6438-113">Bu işlemin denetlenen sürümü denetimleri yoksayar.</span><span class="sxs-lookup"><span data-stu-id="b6438-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6438-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b6438-114">See Also</span></span>

- [<span data-ttu-id="b6438-115">Microsoft. hisse. Iç. onaylama</span><span class="sxs-lookup"><span data-stu-id="b6438-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)