---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Toplam işlem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: 7758e29c9f08f4d05253defbe5a43a5316289522
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221802"
---
# <a name="sum-operation"></a><span data-ttu-id="2983d-102">Toplam işlem</span><span class="sxs-lookup"><span data-stu-id="2983d-102">Sum operation</span></span>

<span data-ttu-id="2983d-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2983d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2983d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2983d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2983d-105">Ters çevrilebilir bir toplam kapısı uygular.</span><span class="sxs-lookup"><span data-stu-id="2983d-105">Implements a reversible sum gate.</span></span> <span data-ttu-id="2983d-106">, Qubit `carryIn` ve ile kodlanmış iki summand bit ile kodlanmış bir birlikte alma bit ve `summand1` ve ' de ve, `summand2` `carryIn` `summand1` `summand2` qubit 'in bit düzeyinde xor değeri hesaplar `summand2` .</span><span class="sxs-lookup"><span data-stu-id="2983d-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.</span></span>

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2983d-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="2983d-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="2983d-108">carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2983d-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2983d-109">Devam eden qubit.</span><span class="sxs-lookup"><span data-stu-id="2983d-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="2983d-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2983d-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2983d-111">İlk summve qubit.</span><span class="sxs-lookup"><span data-stu-id="2983d-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="2983d-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2983d-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2983d-113">İkinci summand qubit, ve toplamının alt bitimiyle değiştirilmiştir `summand1` `summand2` .</span><span class="sxs-lookup"><span data-stu-id="2983d-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2983d-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2983d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2983d-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2983d-115">Remarks</span></span>

<span data-ttu-id="2983d-116">`Carry`İşlemin aksine, bu, yerine getirme bitini hesaplamaz.</span><span class="sxs-lookup"><span data-stu-id="2983d-116">In contrast to the `Carry` operation, this does not compute the carry-out bit.</span></span>