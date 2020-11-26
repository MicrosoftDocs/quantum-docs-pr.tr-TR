---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196183"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="4f444-102">SequentialModel Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="4f444-102">SequentialModel user defined type</span></span>

<span data-ttu-id="4f444-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4f444-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4f444-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4f444-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="4f444-105">Parametreli ve denetimli bir döndürmeler dizisinin, döndürme açılarından oluşan bir atamanın ve model tarafından tanınan iki sınıf arasındaki bir sapıcının oluşan bir hisse</span><span class="sxs-lookup"><span data-stu-id="4f444-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="4f444-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="4f444-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="4f444-107">Yapı: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="4f444-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="4f444-108">Girişleri sınıflandırmak için kullanılan denetlenen döndürmeler dizisi.</span><span class="sxs-lookup"><span data-stu-id="4f444-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="4f444-109">Parametreler: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4f444-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4f444-110">Verilen sınıflandırma yapısına döndürme açıların atanması.</span><span class="sxs-lookup"><span data-stu-id="4f444-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="4f444-111">Sapma: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4f444-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4f444-112">Bu sınıflandırıcı tarafından tanınan iki sınıf arasındaki sapma.</span><span class="sxs-lookup"><span data-stu-id="4f444-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="4f444-113">Başvurular</span><span class="sxs-lookup"><span data-stu-id="4f444-113">References</span></span>

- [<span data-ttu-id="4f444-114">Arxıv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="4f444-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)