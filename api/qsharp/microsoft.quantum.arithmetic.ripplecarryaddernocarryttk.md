---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: Ripptacarryaddernocarryttk işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 59451b4f5c992f900a27139332059af7427b9b93
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730490"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="e26cd-102">Ripptacarryaddernocarryttk işlemi</span><span class="sxs-lookup"><span data-stu-id="e26cd-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="e26cd-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e26cd-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e26cd-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e26cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e26cd-105">Tersine çevrilebilir, yerinde Ripple-çıkış yapmadan iki tamsayının eklenmesini yerine getirme.</span><span class="sxs-lookup"><span data-stu-id="e26cd-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="e26cd-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e26cd-106">Description</span></span>

<span data-ttu-id="e26cd-107">Litttaendian Yazmaçları içinde kodlanmış iki $n $ bit tamsayı verildiğinde `xs` `ys` , işlem, iki tamsayı olan $2 ^ n $ sayısının toplamını hesaplar; burada $n $, girişlerin bit boyutudur `xs` ve `ys` .</span><span class="sxs-lookup"><span data-stu-id="e26cd-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="e26cd-108">Bu, yerine getirme bitini hesaplamaz.</span><span class="sxs-lookup"><span data-stu-id="e26cd-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="e26cd-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="e26cd-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="e26cd-110">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e26cd-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e26cd-111">Litttaendian qubit yazmaç ilk tamsayı summand ' i çağırır.</span><span class="sxs-lookup"><span data-stu-id="e26cd-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="e26cd-112">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e26cd-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e26cd-113">Litttaendian qubit yazmaç ikinci tamsayı summve, toplamın $n $ en az önemli bitini tutacak şekilde değiştirildi.</span><span class="sxs-lookup"><span data-stu-id="e26cd-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e26cd-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e26cd-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e26cd-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e26cd-115">Remarks</span></span>

<span data-ttu-id="e26cd-116">Bu işlem, Ripppercarryadderttk ile aynı işlevselliğe sahiptir, ancak taşıma bitini döndürmez.</span><span class="sxs-lookup"><span data-stu-id="e26cd-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="e26cd-117">Referanslar</span><span class="sxs-lookup"><span data-stu-id="e26cd-117">References</span></span>

- <span data-ttu-id="e26cd-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "hisse toplama devreleri ve sınırlandırılmamış fan-Out", hisse bilgisi ve hesaplama, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="e26cd-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530