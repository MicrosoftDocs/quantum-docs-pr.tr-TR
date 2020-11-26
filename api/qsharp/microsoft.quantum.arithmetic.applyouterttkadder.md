---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: aed15a4d1f3ca7121d6da665f5c08442fd495619
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190624"
---
# <a name="applyouterttkadder-operation"></a><span data-ttu-id="d517f-102">ApplyOuterTTKAdder işlemi</span><span class="sxs-lookup"><span data-stu-id="d517f-102">ApplyOuterTTKAdder operation</span></span>

<span data-ttu-id="d517f-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d517f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d517f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d517f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d517f-105">Tam Adder oluşturmak üzere iç işlemin eşlenmesine izin vermek için Ripptacarryadderttk için dış işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="d517f-105">Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.</span></span>

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d517f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d517f-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d517f-107">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d517f-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d517f-108">Litttaendian qubit, birinci tamsayı summand girişini Ripptacarryadderttk öğesine kaydeder.</span><span class="sxs-lookup"><span data-stu-id="d517f-108">LittleEndian qubit register encoding the first integer summand input to RippleCarryAdderTTK.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d517f-109">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d517f-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d517f-110">Litttaendian qubit yazmaç ikinci tamsayı summand girişini Ripplicarryadderttk olarak kaydeder.</span><span class="sxs-lookup"><span data-stu-id="d517f-110">LittleEndian qubit register encoding the second integer summand input to RippleCarryAdderTTK.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d517f-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d517f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="d517f-112">Başvurular</span><span class="sxs-lookup"><span data-stu-id="d517f-112">References</span></span>

- <span data-ttu-id="d517f-113">Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "hisse toplama devreleri ve sınırlandırılmamış fan-Out", hisse bilgisi ve hesaplama, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="d517f-113">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530