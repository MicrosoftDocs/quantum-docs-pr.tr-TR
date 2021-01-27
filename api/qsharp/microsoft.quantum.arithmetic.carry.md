---
uid: Microsoft.Quantum.Arithmetic.Carry
title: İşlemleri taşıma
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843348"
---
# <a name="carry-operation"></a><span data-ttu-id="d1271-102">İşlemleri taşıma</span><span class="sxs-lookup"><span data-stu-id="d1271-102">Carry operation</span></span>

<span data-ttu-id="d1271-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d1271-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d1271-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1271-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1271-105">Ters bir taşıma geçidi uygular.</span><span class="sxs-lookup"><span data-stu-id="d1271-105">Implements a reversible carry gate.</span></span> <span data-ttu-id="d1271-106">, Qubit `carryIn` ve ile kodlanmış iki summand bit olarak kodlanmış bir taşıma bit değeri verildiğinden ve bit `summand1` `summand2` düzeyinde xor, `carryIn` `summand1` `summand2` qubit ve `summand2` XORed ise qubit ile birlikte kullanılır `carryOut` .</span><span class="sxs-lookup"><span data-stu-id="d1271-106">Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.</span></span>

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d1271-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="d1271-107">Input</span></span>

### <a name="carryin--qubit"></a><span data-ttu-id="d1271-108">carryIn: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d1271-108">carryIn : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d1271-109">Devam eden qubit.</span><span class="sxs-lookup"><span data-stu-id="d1271-109">Carry-in qubit.</span></span>


### <a name="summand1--qubit"></a><span data-ttu-id="d1271-110">summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d1271-110">summand1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d1271-111">İlk summve qubit.</span><span class="sxs-lookup"><span data-stu-id="d1271-111">First summand qubit.</span></span>


### <a name="summand2--qubit"></a><span data-ttu-id="d1271-112">summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d1271-112">summand2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d1271-113">İkinci summand qubit, ve toplamının alt bitimiyle değiştirilmiştir `summand1` `summand2` .</span><span class="sxs-lookup"><span data-stu-id="d1271-113">Second summand qubit, is replaced with the lower bit of the sum of `summand1` and `summand2`.</span></span>


### <a name="carryout--qubit"></a><span data-ttu-id="d1271-114">carryOut: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d1271-114">carryOut : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d1271-115">Yerine getirme qubit, toplamın daha yüksek bitine sahip XORed olacaktır.</span><span class="sxs-lookup"><span data-stu-id="d1271-115">Carry-out qubit, will be xored with the higher bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1271-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1271-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

