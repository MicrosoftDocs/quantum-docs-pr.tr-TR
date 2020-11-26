---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225355"
---
# <a name="blockencodingtoreflection-function"></a><span data-ttu-id="88054-102">BlockEncodingToReflection işlevi</span><span class="sxs-lookup"><span data-stu-id="88054-102">BlockEncodingToReflection function</span></span>

<span data-ttu-id="88054-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="88054-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="88054-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88054-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88054-105">Bir `BlockEncoding` eşdeğerini bir eşdeğerine dönüştürür `BLockEncodingReflection` .</span><span class="sxs-lookup"><span data-stu-id="88054-105">Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.</span></span>

<span data-ttu-id="88054-106">Diğer bir deyişle, `BlockEncoding` bazı işleci $H $ ' i kodlayan bir Unitary $U $ verildiğinde, onu `BlockEncodingReflection` aynı işleci kodlayan $U ' $ içine dönüştürür, ancak aynı zamanda ' ^ \leger = U ' $ $U de karşılar.</span><span class="sxs-lookup"><span data-stu-id="88054-106">That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$.</span></span>
<span data-ttu-id="88054-107">Bu, $U $ öğesinin yardımcı kaydının boyutunu bir qubit artırır.</span><span class="sxs-lookup"><span data-stu-id="88054-107">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="88054-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="88054-108">Input</span></span>

### <a name="blockencoding--blockencoding"></a><span data-ttu-id="88054-109">Blockenkodlama: [Blockenkodlama](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span><span class="sxs-lookup"><span data-stu-id="88054-109">blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)</span></span>

<span data-ttu-id="88054-110">`BlockEncoding`Bir yansımaya dönüştürülecek bir Unitary $U $.</span><span class="sxs-lookup"><span data-stu-id="88054-110">A `BlockEncoding` unitary $U$ to be converted into a reflection.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="88054-111">Çıkış: [Blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="88054-111">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="88054-112">Bir Unitary $U ' $, Yazmaçları üzerinde ortaklaşa bulunan `a` ve `s` Bu blok-kodlama $H $ $U ve ' ^ \hanger = U ' $ karşılar.</span><span class="sxs-lookup"><span data-stu-id="88054-112">A unitary $U'$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^\dagger = U'$.</span></span>

## <a name="remarks"></a><span data-ttu-id="88054-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="88054-113">Remarks</span></span>

<span data-ttu-id="88054-114">Bu, $U $ öğesinin yardımcı kaydının boyutunu bir qubit artırır.</span><span class="sxs-lookup"><span data-stu-id="88054-114">This increases the size of the auxiliary register of $U$ by one qubit.</span></span>

## <a name="references"></a><span data-ttu-id="88054-115">Başvurular</span><span class="sxs-lookup"><span data-stu-id="88054-115">References</span></span>

- <span data-ttu-id="88054-116">Hamiltonian simülasyonu, Qubitiş, Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="88054-116">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="88054-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="88054-117">See Also</span></span>

- [<span data-ttu-id="88054-118">Microsoft. hisse. simülasyon. Blockenkodlama</span><span class="sxs-lookup"><span data-stu-id="88054-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="88054-119">Microsoft. hisse. simülasyon. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="88054-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)