---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderD
title: Ripptacarryadderd işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderD
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: f0f6f39fbff9f682f8f74a982c0a41847df1397a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842960"
---
# <a name="ripplecarryadderd-operation"></a><span data-ttu-id="5a048-102">Ripptacarryadderd işlemi</span><span class="sxs-lookup"><span data-stu-id="5a048-102">RippleCarryAdderD operation</span></span>

<span data-ttu-id="5a048-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5a048-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5a048-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a048-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a048-105">Tersine çevrilebilir, yerinde Ripple-iki tamsayının eklenmesini taşır.</span><span class="sxs-lookup"><span data-stu-id="5a048-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="5a048-106">Litttaendian Yazmaçları ve ile kodlanmış iki $n $-bit tamsayılar `xs` ve `ys` bir qubit,, işlem, sonucun $n $ en düşük önemli bitlerinin içinde tutulduğu iki tamsayının toplamını hesaplar `ys` `carry` .</span><span class="sxs-lookup"><span data-stu-id="5a048-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderD (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5a048-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="5a048-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="5a048-108">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5a048-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5a048-109">Litttaendian qubit yazmaç ilk tamsayı summand ' i çağırır.</span><span class="sxs-lookup"><span data-stu-id="5a048-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="5a048-110">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5a048-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5a048-111">Litttaendian qubit yazmaç ikinci tamsayı summve, toplamın $n $ en az önemli bitini tutacak şekilde değiştirildi.</span><span class="sxs-lookup"><span data-stu-id="5a048-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="5a048-112">taşır: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5a048-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5a048-113">Qubit ' i taşır, toplamın en önemli biti ile XORed.</span><span class="sxs-lookup"><span data-stu-id="5a048-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5a048-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5a048-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5a048-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5a048-115">Remarks</span></span>

<span data-ttu-id="5a048-116">Belirtilen denetlenen işlem, her işleme bir denetim ekleyen varsayılan uygulamada geliştirme yapmak için simetri ve karşılıklı işlem iptali kullanımını sağlar.</span><span class="sxs-lookup"><span data-stu-id="5a048-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="5a048-117">Başvurular</span><span class="sxs-lookup"><span data-stu-id="5a048-117">References</span></span>

- <span data-ttu-id="5a048-118">Thomas G. Draper: "hisse bir bilgisayara ek ekleme", 2000.</span><span class="sxs-lookup"><span data-stu-id="5a048-118">Thomas G. Draper: "Addition on a Quantum Computer", 2000.</span></span>
  https://arxiv.org/abs/quant-ph/0008033