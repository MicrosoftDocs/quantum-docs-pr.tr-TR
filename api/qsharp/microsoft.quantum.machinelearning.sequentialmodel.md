---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854888"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="1981d-102">SequentialModel Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="1981d-102">SequentialModel user defined type</span></span>

<span data-ttu-id="1981d-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1981d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="1981d-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="1981d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="1981d-105">Parametreli ve denetimli bir döndürmeler dizisinin, döndürme açılarından oluşan bir atamanın ve model tarafından tanınan iki sınıf arasındaki bir sapıcının oluşan bir hisse</span><span class="sxs-lookup"><span data-stu-id="1981d-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="1981d-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="1981d-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="1981d-107">Yapı: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="1981d-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="1981d-108">Girişleri sınıflandırmak için kullanılan denetlenen döndürmeler dizisi.</span><span class="sxs-lookup"><span data-stu-id="1981d-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="1981d-109">Parametreler: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="1981d-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="1981d-110">Verilen sınıflandırma yapısına döndürme açıların atanması.</span><span class="sxs-lookup"><span data-stu-id="1981d-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="1981d-111">Sapma: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1981d-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1981d-112">Bu sınıflandırıcı tarafından tanınan iki sınıf arasındaki sapma.</span><span class="sxs-lookup"><span data-stu-id="1981d-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="1981d-113">Başvurular</span><span class="sxs-lookup"><span data-stu-id="1981d-113">References</span></span>

- [<span data-ttu-id="1981d-114">Arxıv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="1981d-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)