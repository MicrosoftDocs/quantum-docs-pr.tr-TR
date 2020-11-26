---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: Rightkaydırıcı işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219524"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="c30d8-102">Rightkaydırıcı işlevi</span><span class="sxs-lookup"><span data-stu-id="c30d8-102">RightShiftedL function</span></span>

<span data-ttu-id="c30d8-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="c30d8-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="c30d8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c30d8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c30d8-105">Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sağa kaydırır.</span><span class="sxs-lookup"><span data-stu-id="c30d8-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="c30d8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c30d8-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="c30d8-107">değer: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c30d8-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c30d8-108">Bit düzeyinde temsilinin sağına kaydırılacağı sayı (daha az önemli).</span><span class="sxs-lookup"><span data-stu-id="c30d8-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="c30d8-109">tutar: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c30d8-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c30d8-110">`value`Sağa kaydırılacağı bit sayısı.</span><span class="sxs-lookup"><span data-stu-id="c30d8-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="c30d8-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c30d8-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c30d8-112">Değeri `value` , bitler tarafından sağa kaydırılan değer `amount` .</span><span class="sxs-lookup"><span data-stu-id="c30d8-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="c30d8-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c30d8-113">Remarks</span></span>

<span data-ttu-id="c30d8-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="c30d8-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```