---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731583"
---
# <a name="dividei-operation"></a><span data-ttu-id="11cb3-102">DivideI işlemi</span><span class="sxs-lookup"><span data-stu-id="11cb3-102">DivideI operation</span></span>

<span data-ttu-id="11cb3-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="11cb3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="11cb3-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="11cb3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="11cb3-105">İki hisse tamsayının böler.</span><span class="sxs-lookup"><span data-stu-id="11cb3-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="11cb3-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="11cb3-106">Description</span></span>

<span data-ttu-id="11cb3-107">`xs` kalanı tutar `xs - floor(xs/ys) * ys` ve `result` tutacaktır `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="11cb3-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="11cb3-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="11cb3-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="11cb3-109">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="11cb3-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="11cb3-110">$n $-bit bölünmeleri, kalanı ile değiştirilirler.</span><span class="sxs-lookup"><span data-stu-id="11cb3-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="11cb3-111">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="11cb3-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="11cb3-112">$n $ bit bölen</span><span class="sxs-lookup"><span data-stu-id="11cb3-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="11cb3-113">Sonuç: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="11cb3-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="11cb3-114">$n $-bit sonucu, başlangıçta $ \ket $ durumunda olmalıdır {0} ve tamsayı bölümünün sonucuyla değiştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="11cb3-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="11cb3-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11cb3-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="11cb3-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="11cb3-116">Remarks</span></span>

<span data-ttu-id="11cb3-117">Bölme uygulamak için standart bir kaydırma ve çıkarma yaklaşımı kullanır.</span><span class="sxs-lookup"><span data-stu-id="11cb3-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="11cb3-118">Denetlenen sürüm, çıkarma işlemi için ek denetimler gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="11cb3-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>