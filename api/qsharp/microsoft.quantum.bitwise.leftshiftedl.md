---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: Leftlatedl işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842150"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="97b51-102">Leftlatedl işlevi</span><span class="sxs-lookup"><span data-stu-id="97b51-102">LeftShiftedL function</span></span>

<span data-ttu-id="97b51-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="97b51-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="97b51-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97b51-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97b51-105">Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sola kaydırır.</span><span class="sxs-lookup"><span data-stu-id="97b51-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="97b51-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="97b51-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="97b51-107">değer: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="97b51-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="97b51-108">Bit düzeyinde temsilinin sola kaydırılacağı sayı (daha fazla önemli).</span><span class="sxs-lookup"><span data-stu-id="97b51-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="97b51-109">tutar: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97b51-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97b51-110">`value`Sola kaydırılacağı bit sayısı.</span><span class="sxs-lookup"><span data-stu-id="97b51-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="97b51-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="97b51-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="97b51-112">`value`Bit olarak sola kaydırılan değeri `amount` .</span><span class="sxs-lookup"><span data-stu-id="97b51-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="97b51-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="97b51-113">Remarks</span></span>

<span data-ttu-id="97b51-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="97b51-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```