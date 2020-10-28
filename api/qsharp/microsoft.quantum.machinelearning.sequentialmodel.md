---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732298"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="4c45a-102">SequentialModel Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="4c45a-102">SequentialModel user defined type</span></span>

<span data-ttu-id="4c45a-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4c45a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4c45a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c45a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c45a-105">Parametreli ve denetimli bir döndürmeler dizisinin, döndürme açılarından oluşan bir atamanın ve model tarafından tanınan iki sınıf arasındaki bir sapıcının oluşan bir hisse</span><span class="sxs-lookup"><span data-stu-id="4c45a-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="4c45a-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="4c45a-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="4c45a-107">Yapı: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="4c45a-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="4c45a-108">Girişleri sınıflandırmak için kullanılan denetlenen döndürmeler dizisi.</span><span class="sxs-lookup"><span data-stu-id="4c45a-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="4c45a-109">Parametreler: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4c45a-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4c45a-110">Verilen sınıflandırma yapısına döndürme açıların atanması.</span><span class="sxs-lookup"><span data-stu-id="4c45a-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="4c45a-111">Sapma: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4c45a-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4c45a-112">Bu sınıflandırıcı tarafından tanınan iki sınıf arasındaki sapma.</span><span class="sxs-lookup"><span data-stu-id="4c45a-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="4c45a-113">Referanslar</span><span class="sxs-lookup"><span data-stu-id="4c45a-113">References</span></span>

- [<span data-ttu-id="4c45a-114">Arxıv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="4c45a-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)