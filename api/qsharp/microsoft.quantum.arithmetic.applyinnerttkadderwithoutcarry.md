---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 656dc947ab88a7e7f1e8e8722c5262470307f7dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190964"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="d658f-102">ApplyInnerTTKAdderWithoutCarry işlemi</span><span class="sxs-lookup"><span data-stu-id="d658f-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="d658f-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d658f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d658f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d658f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d658f-105">Ripptacarryaddernocarryttk işlemi için iç Toplama işlevini uygular.</span><span class="sxs-lookup"><span data-stu-id="d658f-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="d658f-106">Bu, tam Adder oluşturmak için dıştaki işlemle Birleşik işlem olan iç işlemdir.</span><span class="sxs-lookup"><span data-stu-id="d658f-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d658f-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="d658f-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d658f-108">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d658f-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d658f-109">Litttaendian qubit yazmaç birinci tamsayı summand girişi ile Ripptacarryaddernocarryttk.</span><span class="sxs-lookup"><span data-stu-id="d658f-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d658f-110">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d658f-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d658f-111">Litttaendian qubit yazmaç ikinci tamsayı summand girişi ile Ripptacarryaddernocarryttk.</span><span class="sxs-lookup"><span data-stu-id="d658f-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d658f-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d658f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d658f-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d658f-113">Remarks</span></span>

<span data-ttu-id="d658f-114">Belirtilen denetlenen işlem, her işleme bir denetim ekleyen varsayılan uygulamada geliştirme yapmak için simetri ve karşılıklı işlem iptali kullanımını sağlar.</span><span class="sxs-lookup"><span data-stu-id="d658f-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="d658f-115">Başvurular</span><span class="sxs-lookup"><span data-stu-id="d658f-115">References</span></span>

- <span data-ttu-id="d658f-116">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "hisse toplama devreleri ve sınırlandırılmamış fan-Out", hisse bilgisi ve hesaplama, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="d658f-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530