---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: Compareusingripptago işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: e2d6e5a663f8c4e101c7e2ab1346d10cade3f4e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223468"
---
# <a name="compareusingripplecarry-operation"></a><span data-ttu-id="e2713-102">Compareusingripptago işlemi</span><span class="sxs-lookup"><span data-stu-id="e2713-102">CompareUsingRippleCarry operation</span></span>

<span data-ttu-id="e2713-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e2713-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e2713-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2713-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e2713-105">Bu işlem, qubits 'in bir yazmacından temsil edilen bir tamsayı başka bir tamsayıdır daha büyükse, bir çıkış qubit üzerine bir XOR sonucu uygulayarak sınar.</span><span class="sxs-lookup"><span data-stu-id="e2713-105">This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.</span></span>

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e2713-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e2713-106">Description</span></span>

<span data-ttu-id="e2713-107">İki tamsayı verildiğinde `x` ve `y` eşit boyutlu qubit Yazmaçları içinde depolanan bu işlem, karşılayıp karşılamadığını denetler `x > y` .</span><span class="sxs-lookup"><span data-stu-id="e2713-107">Given two integers `x` and `y` stored in equal-size qubit registers, this operation checks if they satisfy `x > y`.</span></span> <span data-ttu-id="e2713-108">True ise, 1 çıkış qubit XORed.</span><span class="sxs-lookup"><span data-stu-id="e2713-108">If true, 1 is XORed into an output qubit.</span></span> <span data-ttu-id="e2713-109">Aksi halde, 0 bir çıkış qubit içine XORed.</span><span class="sxs-lookup"><span data-stu-id="e2713-109">Otherwise, 0 is XORed into an output qubit.</span></span>
<span data-ttu-id="e2713-110">Diğer bir deyişle, bu işlem Unitary $ $ \begin{hizalaması} U\ket {x} \ ayraç {y} \ demet {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)} tarafından temsil edilebilir.</span><span class="sxs-lookup"><span data-stu-id="e2713-110">In other words, this operation can be represented by the unitary $$ \begin{align} U\ket{x}\ket{y}\ket{z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.</span></span>
<span data-ttu-id="e2713-111">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="e2713-111">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="e2713-112">Giriş</span><span class="sxs-lookup"><span data-stu-id="e2713-112">Input</span></span>

### <a name="x--littleendian"></a><span data-ttu-id="e2713-113">x: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e2713-113">x : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e2713-114">`LittleEndian`Bir qubit kasada saklanan biçimde Karşılaştırılacak ilk numara.</span><span class="sxs-lookup"><span data-stu-id="e2713-114">First number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="y--littleendian"></a><span data-ttu-id="e2713-115">y: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e2713-115">y : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e2713-116">Bir qubit kasada saklanan şekilde karşılaştırılan ikinci sayı `LittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="e2713-116">Second number to be compared stored in `LittleEndian` format in a qubit register.</span></span>


### <a name="output--qubit"></a><span data-ttu-id="e2713-117">Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e2713-117">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e2713-118">$X>y $ karşılaştırma sonucunu depolayan qubit.</span><span class="sxs-lookup"><span data-stu-id="e2713-118">Qubit that stores the result of the comparison $x>y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2713-119">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2713-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e2713-120">Başvurular</span><span class="sxs-lookup"><span data-stu-id="e2713-120">References</span></span>

- <span data-ttu-id="e2713-121">Yeni bir hisse Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span><span class="sxs-lookup"><span data-stu-id="e2713-121">A new quantum ripple-carry addition circuit Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184</span></span>