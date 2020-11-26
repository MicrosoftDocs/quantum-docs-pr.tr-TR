---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Leftkaydırıcı Tedi işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209868"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="89dd4-102">Leftkaydırıcı Tedi işlevi</span><span class="sxs-lookup"><span data-stu-id="89dd4-102">LeftShiftedI function</span></span>

<span data-ttu-id="89dd4-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="89dd4-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="89dd4-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89dd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89dd4-105">Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sola kaydırır.</span><span class="sxs-lookup"><span data-stu-id="89dd4-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="89dd4-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="89dd4-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="89dd4-107">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89dd4-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89dd4-108">Bit düzeyinde temsilinin sola kaydırılacağı sayı (daha fazla önemli).</span><span class="sxs-lookup"><span data-stu-id="89dd4-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="89dd4-109">tutar: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89dd4-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89dd4-110">`value`Sola kaydırılacağı bit sayısı.</span><span class="sxs-lookup"><span data-stu-id="89dd4-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="89dd4-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="89dd4-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="89dd4-112">`value`Bit olarak sola kaydırılan değeri `amount` .</span><span class="sxs-lookup"><span data-stu-id="89dd4-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="89dd4-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="89dd4-113">Remarks</span></span>

<span data-ttu-id="89dd4-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="89dd4-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```