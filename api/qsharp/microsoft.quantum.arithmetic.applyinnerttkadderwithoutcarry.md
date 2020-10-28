---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 3335c63b8509090deed1172419158da0d5e80409
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731866"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a><span data-ttu-id="4a319-102">ApplyInnerTTKAdderWithoutCarry işlemi</span><span class="sxs-lookup"><span data-stu-id="4a319-102">ApplyInnerTTKAdderWithoutCarry operation</span></span>

<span data-ttu-id="4a319-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4a319-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4a319-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4a319-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4a319-105">Ripptacarryaddernocarryttk işlemi için iç Toplama işlevini uygular.</span><span class="sxs-lookup"><span data-stu-id="4a319-105">Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK.</span></span> <span data-ttu-id="4a319-106">Bu, tam Adder oluşturmak için dıştaki işlemle Birleşik işlem olan iç işlemdir.</span><span class="sxs-lookup"><span data-stu-id="4a319-106">This is the inner operation that is conjugated with the outer operation to construct the full adder.</span></span>

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="4a319-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="4a319-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="4a319-108">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4a319-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4a319-109">Litttaendian qubit yazmaç birinci tamsayı summand girişi ile Ripptacarryaddernocarryttk.</span><span class="sxs-lookup"><span data-stu-id="4a319-109">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderNoCarryTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="4a319-110">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4a319-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4a319-111">Litttaendian qubit yazmaç ikinci tamsayı summand girişi ile Ripptacarryaddernocarryttk.</span><span class="sxs-lookup"><span data-stu-id="4a319-111">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderNoCarryTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a319-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a319-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4a319-113">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="4a319-113">Remarks</span></span>

<span data-ttu-id="4a319-114">Belirtilen denetlenen işlem, her işleme bir denetim ekleyen varsayılan uygulamada geliştirme yapmak için simetri ve karşılıklı işlem iptali kullanımını sağlar.</span><span class="sxs-lookup"><span data-stu-id="4a319-114">The specified controlled operation makes use of symmetry and mutual cancellation of operations to improve on the default implementation that adds a control to every operation.</span></span>

## <a name="references"></a><span data-ttu-id="4a319-115">Referanslar</span><span class="sxs-lookup"><span data-stu-id="4a319-115">References</span></span>

- <span data-ttu-id="4a319-116">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "hisse toplama devreleri ve sınırlandırılmamış fan-Out", hisse bilgisi ve hesaplama, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="4a319-116">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530