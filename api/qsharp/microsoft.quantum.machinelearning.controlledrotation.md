---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847403"
---
# <a name="controlledrotation-user-defined-type"></a><span data-ttu-id="3e7f9-102">ControlledRotation Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="3e7f9-102">ControlledRotation user defined type</span></span>

<span data-ttu-id="3e7f9-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3e7f9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="3e7f9-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="3e7f9-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="3e7f9-105">Hedef ve denetim dizinleri, döndürme ekseni ve Dizin bir model parametresi vektörüne göre denetimli bir döndürmeyi açıklar.</span><span class="sxs-lookup"><span data-stu-id="3e7f9-105">Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.</span></span>

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a><span data-ttu-id="3e7f9-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="3e7f9-106">Named Items</span></span>

### <a name="targetindex--int"></a><span data-ttu-id="3e7f9-107">Targetındex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e7f9-107">TargetIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e7f9-108">Bu denetimli döndürme için hedef qubit dizini.</span><span class="sxs-lookup"><span data-stu-id="3e7f9-108">Index of the target qubit for this controlled rotation.</span></span>
### <a name="controlindices--int"></a><span data-ttu-id="3e7f9-109">Controlindıces: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3e7f9-109">ControlIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3e7f9-110">Bu döndürme için bir denetim qubit dizinleri dizisi.</span><span class="sxs-lookup"><span data-stu-id="3e7f9-110">An array of the control qubit indices for this rotation.</span></span>
### <a name="axis--pauli"></a><span data-ttu-id="3e7f9-111">Eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="3e7f9-111">Axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="3e7f9-112">Bu döndürme için eksen.</span><span class="sxs-lookup"><span data-stu-id="3e7f9-112">The axis for this rotation.</span></span>
### <a name="parameterindex--int"></a><span data-ttu-id="3e7f9-113">ParameterIndex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e7f9-113">ParameterIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e7f9-114">Bu döndürme açısını açıklayan bir model parametresi vektörüne bir dizin.</span><span class="sxs-lookup"><span data-stu-id="3e7f9-114">An index into a model parameter vector describing the angle for this rotation.</span></span>

## <a name="example"></a><span data-ttu-id="3e7f9-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="3e7f9-115">Example</span></span>

<span data-ttu-id="3e7f9-116">Aşağıda, bir kayıttaki ilk qubitin $X $ ekseni ile ilgili bir döndürme ve ikinci qubit üzerinde denetlenen ve ardışık bir modeldeki dördüncü parametre tarafından verilen bir açı gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="3e7f9-116">The following represents a rotation about the $X$-axis of the first qubit in a register, controlled on the second qubit, and with an angle given by the fourth parameter in a sequential model:</span></span>

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a><span data-ttu-id="3e7f9-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3e7f9-117">Remarks</span></span>

<span data-ttu-id="3e7f9-118">Denetlenmeyen bir döndürme `ControlIndices` , boş bir dizin dizisine ayarlanarak gösterilebilir `new Int[0]` .</span><span class="sxs-lookup"><span data-stu-id="3e7f9-118">An uncontrolled rotation can be represented by setting `ControlIndices` to an empty array of indexes, `new Int[0]`.</span></span>