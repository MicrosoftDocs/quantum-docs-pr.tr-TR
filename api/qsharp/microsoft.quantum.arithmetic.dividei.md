---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846677"
---
# <a name="dividei-operation"></a><span data-ttu-id="27674-102">DivideI işlemi</span><span class="sxs-lookup"><span data-stu-id="27674-102">DivideI operation</span></span>

<span data-ttu-id="27674-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="27674-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="27674-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="27674-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="27674-105">İki hisse tamsayının böler.</span><span class="sxs-lookup"><span data-stu-id="27674-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="27674-106">Description</span><span class="sxs-lookup"><span data-stu-id="27674-106">Description</span></span>

<span data-ttu-id="27674-107">`xs` kalanı tutar `xs - floor(xs/ys) * ys` ve `result` tutacaktır `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="27674-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="27674-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="27674-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="27674-109">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="27674-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="27674-110">$n $-bit bölünmeleri, kalanı ile değiştirilirler.</span><span class="sxs-lookup"><span data-stu-id="27674-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="27674-111">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="27674-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="27674-112">$n $ bit bölen</span><span class="sxs-lookup"><span data-stu-id="27674-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="27674-113">Sonuç: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="27674-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="27674-114">$n $-bit sonucu, başlangıçta $ \ket $ durumunda olmalıdır {0} ve tamsayı bölümünün sonucuyla değiştirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="27674-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27674-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27674-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="27674-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="27674-116">Remarks</span></span>

<span data-ttu-id="27674-117">Bölme uygulamak için standart bir kaydırma ve çıkarma yaklaşımı kullanır.</span><span class="sxs-lookup"><span data-stu-id="27674-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="27674-118">Denetlenen sürüm, çıkarma işlemi için ek denetimler gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="27674-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>