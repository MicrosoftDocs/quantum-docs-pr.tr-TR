---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 23c1f6dcdf3894cf1b416efd922c9eed01ac8f85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731874"
---
# <a name="applyinnerttkadder-operation"></a><span data-ttu-id="2e77d-102">ApplyInnerTTKAdder işlemi</span><span class="sxs-lookup"><span data-stu-id="2e77d-102">ApplyInnerTTKAdder operation</span></span>

<span data-ttu-id="2e77d-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2e77d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2e77d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e77d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e77d-105">Ripptacarryadderttk işlemi için iç Toplama işlevini uygular.</span><span class="sxs-lookup"><span data-stu-id="2e77d-105">Implements the inner addition function for the operation RippleCarryAdderTTK.</span></span> <span data-ttu-id="2e77d-106">Bu, tam Adder oluşturmak için dıştaki işlemle Birleşik işlem olan iç işlemdir.</span><span class="sxs-lookup"><span data-stu-id="2e77d-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="2e77d-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="2e77d-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="2e77d-108">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2e77d-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2e77d-109">Litttaendian qubit, birinci tamsayı summand girişini Ripptacarryadderttk öğesine kaydeder.</span><span class="sxs-lookup"><span data-stu-id="2e77d-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="2e77d-110">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2e77d-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2e77d-111">Litttaendian qubit yazmaç ikinci tamsayı summand girişini Ripplicarryadderttk olarak kaydeder.</span><span class="sxs-lookup"><span data-stu-id="2e77d-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="2e77d-112">taşır: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2e77d-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2e77d-113">Qubit ' i taşır, toplamın en önemli biti ile XORed.</span><span class="sxs-lookup"><span data-stu-id="2e77d-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e77d-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e77d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2e77d-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2e77d-115">Remarks</span></span>

<span data-ttu-id="2e77d-116">Belirtilen denetlenen işlem, her işleme bir denetim ekleyen varsayılan uygulamada geliştirme yapmak için simetri ve karşılıklı işlem iptali kullanımını sağlar.</span><span class="sxs-lookup"><span data-stu-id="2e77d-116">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="2e77d-117">Referanslar</span><span class="sxs-lookup"><span data-stu-id="2e77d-117">References</span></span>

- <span data-ttu-id="2e77d-118">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "hisse toplama devreleri ve sınırlandırılmamış fan-Out", hisse bilgisi ve hesaplama, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="2e77d-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530