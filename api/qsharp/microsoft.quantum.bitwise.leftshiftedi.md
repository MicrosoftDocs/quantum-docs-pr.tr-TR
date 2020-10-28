---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Leftkaydırıcı Tedi işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729879"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="71f88-102">Leftkaydırıcı Tedi işlevi</span><span class="sxs-lookup"><span data-stu-id="71f88-102">LeftShiftedI function</span></span>

<span data-ttu-id="71f88-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="71f88-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="71f88-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="71f88-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="71f88-105">Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sola kaydırır.</span><span class="sxs-lookup"><span data-stu-id="71f88-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="71f88-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="71f88-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="71f88-107">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71f88-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71f88-108">Bit düzeyinde temsilinin sola kaydırılacağı sayı (daha fazla önemli).</span><span class="sxs-lookup"><span data-stu-id="71f88-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="71f88-109">tutar: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71f88-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71f88-110">`value`Sola kaydırılacağı bit sayısı.</span><span class="sxs-lookup"><span data-stu-id="71f88-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="71f88-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="71f88-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="71f88-112">`value`Bit olarak sola kaydırılan değeri `amount` .</span><span class="sxs-lookup"><span data-stu-id="71f88-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="71f88-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="71f88-113">Remarks</span></span>

<span data-ttu-id="71f88-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="71f88-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```