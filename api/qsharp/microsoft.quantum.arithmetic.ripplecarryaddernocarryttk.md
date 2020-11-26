---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: Ripptacarryaddernocarryttk işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: a539d85a4800c2f4452a1c6fe2c4f88a6296c3e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222006"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="401df-102">Ripptacarryaddernocarryttk işlemi</span><span class="sxs-lookup"><span data-stu-id="401df-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="401df-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="401df-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="401df-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="401df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="401df-105">Tersine çevrilebilir, yerinde Ripple-çıkış yapmadan iki tamsayının eklenmesini yerine getirme.</span><span class="sxs-lookup"><span data-stu-id="401df-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="401df-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="401df-106">Description</span></span>

<span data-ttu-id="401df-107">Litttaendian Yazmaçları içinde kodlanmış iki $n $ bit tamsayı verildiğinde `xs` `ys` , işlem, iki tamsayı olan $2 ^ n $ sayısının toplamını hesaplar; burada $n $, girişlerin bit boyutudur `xs` ve `ys` .</span><span class="sxs-lookup"><span data-stu-id="401df-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="401df-108">Bu, yerine getirme bitini hesaplamaz.</span><span class="sxs-lookup"><span data-stu-id="401df-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="401df-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="401df-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="401df-110">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="401df-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="401df-111">Litttaendian qubit yazmaç ilk tamsayı summand ' i çağırır.</span><span class="sxs-lookup"><span data-stu-id="401df-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="401df-112">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="401df-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="401df-113">Litttaendian qubit yazmaç ikinci tamsayı summve, toplamın $n $ en az önemli bitini tutacak şekilde değiştirildi.</span><span class="sxs-lookup"><span data-stu-id="401df-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="401df-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="401df-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="401df-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="401df-115">Remarks</span></span>

<span data-ttu-id="401df-116">Bu işlem, Ripppercarryadderttk ile aynı işlevselliğe sahiptir, ancak taşıma bitini döndürmez.</span><span class="sxs-lookup"><span data-stu-id="401df-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="401df-117">Başvurular</span><span class="sxs-lookup"><span data-stu-id="401df-117">References</span></span>

- <span data-ttu-id="401df-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "hisse toplama devreleri ve sınırlandırılmamış fan-Out", hisse bilgisi ve hesaplama, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="401df-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530