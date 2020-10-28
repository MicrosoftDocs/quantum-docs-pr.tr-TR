---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726641"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="2837a-102">ControlledRotation Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="2837a-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="2837a-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2837a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2837a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2837a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2837a-105">Hedef ve denetim dizinleri, döndürme ekseni ve Dizin bir model parametresi vektörüne göre denetimli bir döndürmeyi açıklar.</span><span class="sxs-lookup"><span data-stu-id="2837a-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="2837a-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="2837a-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="2837a-107">Targetındex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2837a-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2837a-108">Bu denetimli döndürme için hedef qubit dizini.</span><span class="sxs-lookup"><span data-stu-id="2837a-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="2837a-109">Controlindıces: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2837a-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2837a-110">Bu döndürme için bir denetim qubit dizinleri dizisi.</span><span class="sxs-lookup"><span data-stu-id="2837a-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="2837a-111">Eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="2837a-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="2837a-112">Bu döndürme için eksen.</span><span class="sxs-lookup"><span data-stu-id="2837a-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="2837a-113">ParameterIndex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2837a-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2837a-114">Bu döndürme açısını açıklayan bir model parametresi vektörüne bir dizin.</span><span class="sxs-lookup"><span data-stu-id="2837a-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="remarks"></a><span data-ttu-id="2837a-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2837a-115">Remarks</span></span>

<span data-ttu-id="2837a-116">Denetlenmeyen bir döndürme `ControlIndices` , boş bir dizin dizisine ayarlanarak gösterilebilir `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="2837a-116">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>