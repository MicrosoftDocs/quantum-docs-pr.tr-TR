---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Ripptacarryaddercdkm işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: 6dcb5193c5d1d059682a79e63e6562aabff7539d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730511"
---
# <a name="ripplecarryaddercdkm-operation"></a><span data-ttu-id="f2a7c-102">Ripptacarryaddercdkm işlemi</span><span class="sxs-lookup"><span data-stu-id="f2a7c-102">RippleCarryAdderCDKM operation</span></span>

<span data-ttu-id="f2a7c-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f2a7c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f2a7c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2a7c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f2a7c-105">Tersine çevrilebilir, yerinde Ripple-iki tamsayının eklenmesini taşır.</span><span class="sxs-lookup"><span data-stu-id="f2a7c-105">Reversible, in-place ripple-carry addition of two integers.</span></span>

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="f2a7c-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f2a7c-106">Description</span></span>

<span data-ttu-id="f2a7c-107">Litttaendian Yazmaçları ve ile kodlanmış iki $n $-bit tamsayılar `xs` ve `ys` bir qubit,, işlem, sonucun $n $ en düşük önemli bitlerinin içinde tutulduğu iki tamsayının toplamını hesaplar `ys` `carry` .</span><span class="sxs-lookup"><span data-stu-id="f2a7c-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

## <a name="input"></a><span data-ttu-id="f2a7c-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="f2a7c-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="f2a7c-109">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f2a7c-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f2a7c-110">Litttaendian qubit yazmaç ilk tamsayı summand ' i çağırır.</span><span class="sxs-lookup"><span data-stu-id="f2a7c-110">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="f2a7c-111">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f2a7c-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f2a7c-112">Litttaendian qubit yazmaç ikinci tamsayı summve, toplamın en az önemli bitini tutacak şekilde değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="f2a7c-112">LittleEndian qubit register encoding the second integer summand, is modified to hold the n least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="f2a7c-113">taşır: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f2a7c-113">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f2a7c-114">Qubit ' i taşır, toplamın en önemli biti ile XORed.</span><span class="sxs-lookup"><span data-stu-id="f2a7c-114">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2a7c-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2a7c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f2a7c-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f2a7c-116">Remarks</span></span>

<span data-ttu-id="f2a7c-117">Bu işlem, Rippelcarryadderd ile aynı işlevselliğe sahiptir, ancak $n $ yerine yalnızca bir yardımcı qubit kullanır.</span><span class="sxs-lookup"><span data-stu-id="f2a7c-117">This operation has the same functionality as RippleCarryAdderD, but only uses one auxiliary qubit instead of $n$.</span></span>

## <a name="references"></a><span data-ttu-id="f2a7c-118">Referanslar</span><span class="sxs-lookup"><span data-stu-id="f2a7c-118">References</span></span>

- <span data-ttu-id="f2a7c-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse</span><span class="sxs-lookup"><span data-stu-id="f2a7c-119">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1