---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223791"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="89f0c-102">AssertMostSignificantBit işlemi</span><span class="sxs-lookup"><span data-stu-id="89f0c-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="89f0c-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="89f0c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="89f0c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89f0c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89f0c-105">Bir qubit kayıt 'nın, işaretsiz bir tamsayıyı temsil eden en önemli qubitin belirli bir durumda olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="89f0c-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="89f0c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="89f0c-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="89f0c-107">değer: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="89f0c-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="89f0c-108">Belirtilmekte olan en yüksek bit değeri.</span><span class="sxs-lookup"><span data-stu-id="89f0c-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="89f0c-109">Sayı: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="89f0c-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="89f0c-110">En yüksek bitin denetlenme işaretsiz tamsayı.</span><span class="sxs-lookup"><span data-stu-id="89f0c-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="89f0c-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89f0c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="89f0c-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="89f0c-112">Remarks</span></span>

<span data-ttu-id="89f0c-113">Bu işlemin denetlenen sürümü denetimleri yoksayar.</span><span class="sxs-lookup"><span data-stu-id="89f0c-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="89f0c-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="89f0c-114">See Also</span></span>

- [<span data-ttu-id="89f0c-115">Microsoft. hisse. Iç. onaylama</span><span class="sxs-lookup"><span data-stu-id="89f0c-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)