---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: 3d6d7c3446075130e5a8ee93abbd27e617d50b3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731810"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="ab52e-102">ApplyOuterTTKAdder işlemi</span><span class="sxs-lookup"><span data-stu-id="ab52e-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="ab52e-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ab52e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ab52e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab52e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab52e-105">Tam Adder oluşturmak üzere iç işlemin eşlenmesine izin vermek için Ripptacarryadderttk için dış işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="ab52e-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="ab52e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ab52e-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="ab52e-107">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ab52e-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ab52e-108">Litttaendian qubit, birinci tamsayı summand girişini Ripptacarryadderttk öğesine kaydeder.</span><span class="sxs-lookup"><span data-stu-id="ab52e-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="ab52e-109">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="ab52e-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="ab52e-110">Litttaendian qubit yazmaç ikinci tamsayı summand girişini Ripplicarryadderttk olarak kaydeder.</span><span class="sxs-lookup"><span data-stu-id="ab52e-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ab52e-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab52e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="ab52e-112">Referanslar</span><span class="sxs-lookup"><span data-stu-id="ab52e-112">References</span></span>

- <span data-ttu-id="ab52e-113">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "hisse toplama devreleri ve sınırlandırılmamış fan-Out", hisse bilgisi ve hesaplama, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="ab52e-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530