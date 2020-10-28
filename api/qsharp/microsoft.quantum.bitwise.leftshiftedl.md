---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Leftlatedl işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729858"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="e083d-102">Leftlatedl işlevi</span><span class="sxs-lookup"><span data-stu-id="e083d-102">LeftShiftedL function</span></span>

<span data-ttu-id="e083d-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="e083d-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="e083d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e083d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e083d-105">Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sola kaydırır.</span><span class="sxs-lookup"><span data-stu-id="e083d-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="e083d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e083d-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="e083d-107">değer: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e083d-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e083d-108">Bit düzeyinde temsilinin sola kaydırılacağı sayı (daha fazla önemli).</span><span class="sxs-lookup"><span data-stu-id="e083d-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="e083d-109">tutar: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e083d-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e083d-110">`value`Sola kaydırılacağı bit sayısı.</span><span class="sxs-lookup"><span data-stu-id="e083d-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="e083d-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e083d-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e083d-112">`value`Bit olarak sola kaydırılan değeri `amount` .</span><span class="sxs-lookup"><span data-stu-id="e083d-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="e083d-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e083d-113">Remarks</span></span>

<span data-ttu-id="e083d-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="e083d-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```