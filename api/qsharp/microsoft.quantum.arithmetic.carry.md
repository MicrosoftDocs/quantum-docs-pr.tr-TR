---
uid: Microsoft.Quantum.Arithmetic.Carry
title: İşlemleri taşıma
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: 53f8d2a8ba89a912e3d4c08452208a899b2b85de
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223604"
---
# <a name="carry-operation"></a><span data-ttu-id="ac769-102">İşlemleri taşıma</span><span class="sxs-lookup"><span data-stu-id="ac769-102">Carry operation</span></span>

<span data-ttu-id="ac769-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ac769-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ac769-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ac769-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ac769-105">Ters bir taşıma geçidi uygular.</span><span class="sxs-lookup"><span data-stu-id="ac769-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="ac769-106">, Qubit `carryIn` ve ile kodlanmış iki summand bit olarak kodlanmış bir taşıma bit değeri verildiğinden ve bit `summand1` `summand2` düzeyinde xor, `carryIn` `summand1` `summand2` qubit ve `summand2` XORed ise qubit ile birlikte kullanılır `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="ac769-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ac769-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="ac769-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="ac769-108">carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac769-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac769-109">Devam eden qubit.</span><span class="sxs-lookup"><span data-stu-id="ac769-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="ac769-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac769-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac769-111">İlk summve qubit.</span><span class="sxs-lookup"><span data-stu-id="ac769-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="ac769-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac769-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac769-113">İkinci summand qubit, ve toplamının alt bitimiyle değiştirilmiştir `summand1` `summand2` .</span><span class="sxs-lookup"><span data-stu-id="ac769-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="ac769-114">carryOut: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac769-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac769-115">Yerine getirme qubit, toplamın daha yüksek bitine sahip XORed olacaktır.</span><span class="sxs-lookup"><span data-stu-id="ac769-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac769-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac769-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

