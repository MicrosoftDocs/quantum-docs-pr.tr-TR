---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: Leftkaydırıcı Tedi işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845299"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="6abdc-102">Leftkaydırıcı Tedi işlevi</span><span class="sxs-lookup"><span data-stu-id="6abdc-102">LeftShiftedI function</span></span>

<span data-ttu-id="6abdc-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="6abdc-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="6abdc-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6abdc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6abdc-105">Bir sayının bit düzeyinde gösterimini verilen bit sayısı ile sola kaydırır.</span><span class="sxs-lookup"><span data-stu-id="6abdc-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="6abdc-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6abdc-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="6abdc-107">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6abdc-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6abdc-108">Bit düzeyinde temsilinin sola kaydırılacağı sayı (daha fazla önemli).</span><span class="sxs-lookup"><span data-stu-id="6abdc-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="6abdc-109">tutar: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6abdc-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6abdc-110">`value`Sola kaydırılacağı bit sayısı.</span><span class="sxs-lookup"><span data-stu-id="6abdc-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="6abdc-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6abdc-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6abdc-112">`value`Bit olarak sola kaydırılan değeri `amount` .</span><span class="sxs-lookup"><span data-stu-id="6abdc-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="6abdc-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6abdc-113">Remarks</span></span>

<span data-ttu-id="6abdc-114">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="6abdc-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```