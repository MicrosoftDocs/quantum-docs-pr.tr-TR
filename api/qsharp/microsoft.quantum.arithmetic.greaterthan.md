---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 553efb0fc83f24235cb4a77933bd1d547bbd1fed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846627"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="2f13f-102">GreaterThan işlemi</span><span class="sxs-lookup"><span data-stu-id="2f13f-102">GreaterThan operation</span></span>

<span data-ttu-id="2f13f-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2f13f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2f13f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f13f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f13f-105">Qubit Yazmaçları ile kodlanmış iki tamsayı arasında bir daha büyüktür karşılaştırması uygular ve karşılaştırmanın sonucuna göre bir hedef qubit alır.</span><span class="sxs-lookup"><span data-stu-id="2f13f-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2f13f-106">Description</span><span class="sxs-lookup"><span data-stu-id="2f13f-106">Description</span></span>

<span data-ttu-id="2f13f-107">$X $ ve $y $, qubit, XS ve YS içinde kodlandığı iki tamsayının karşılaştırmadan kesinlikle daha büyük bir şekilde gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="2f13f-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="2f13f-108">$X y $ >, sonuç qubit çevrilcektir, aksi takdirde sonuç qubit, durumunu korur.</span><span class="sxs-lookup"><span data-stu-id="2f13f-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="2f13f-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="2f13f-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="2f13f-110">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2f13f-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2f13f-111">Litttaendian qubit yazmaç ilk tamsayıyı $x $.</span><span class="sxs-lookup"><span data-stu-id="2f13f-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="2f13f-112">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2f13f-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2f13f-113">Litttaendian qubit yazmaç ikinci tamsayıyı $y $.</span><span class="sxs-lookup"><span data-stu-id="2f13f-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="2f13f-114">Sonuç: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2f13f-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2f13f-115">$X > y $ olarak çevrilmiş tek qubit.</span><span class="sxs-lookup"><span data-stu-id="2f13f-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2f13f-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2f13f-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2f13f-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2f13f-117">Remarks</span></span>

<span data-ttu-id="2f13f-118">$X-y = (x ' + y) ' $ olan eli kullanır, burada ' ise birinin tamamlayıcı olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="2f13f-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="2f13f-119">Başvurular</span><span class="sxs-lookup"><span data-stu-id="2f13f-119">References</span></span>

- <span data-ttu-id="2f13f-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse</span><span class="sxs-lookup"><span data-stu-id="2f13f-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="2f13f-121">Thomas Haümü, MARI Roetteler, Kronysta M. Svore: "düzenleme Toffoli tabanlı modüler çarpma ile 2n + 2 qubit kullanma", 2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="2f13f-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>