---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: Rightkaydırıcı Tedı işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209783"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="9d5f8-102">Rightkaydırıcı Tedı işlevi</span><span class="sxs-lookup"><span data-stu-id="9d5f8-102">RightShiftedI function</span></span>

<span data-ttu-id="9d5f8-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="9d5f8-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="9d5f8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d5f8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d5f8-105">Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sağa kaydırır.</span><span class="sxs-lookup"><span data-stu-id="9d5f8-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="9d5f8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9d5f8-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="9d5f8-107">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d5f8-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d5f8-108">Bit düzeyinde temsilinin sağına kaydırılacağı sayı (daha az önemli).</span><span class="sxs-lookup"><span data-stu-id="9d5f8-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="9d5f8-109">tutar: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d5f8-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d5f8-110">`value`Sağa kaydırılacağı bit sayısı.</span><span class="sxs-lookup"><span data-stu-id="9d5f8-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="9d5f8-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d5f8-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d5f8-112">Değeri `value` , bitler tarafından sağa kaydırılan değer `amount` .</span><span class="sxs-lookup"><span data-stu-id="9d5f8-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d5f8-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="9d5f8-113">Remarks</span></span>

<span data-ttu-id="9d5f8-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="9d5f8-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```