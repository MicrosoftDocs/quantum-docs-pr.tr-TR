---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211976"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="c38d6-102">CombinedStructure işlevi</span><span class="sxs-lookup"><span data-stu-id="c38d6-102">CombinedStructure function</span></span>

<span data-ttu-id="c38d6-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c38d6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c38d6-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c38d6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="c38d6-105">Denetlenen bir veya daha fazla yönetim katmanı, farklı katmanlar ayrı model parametrelerine göre parametreleştirileyecek şekilde, model parametre dizini kaydırılan tek bir katman döndürür.</span><span class="sxs-lookup"><span data-stu-id="c38d6-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="c38d6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c38d6-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="c38d6-107">katmanlar: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="c38d6-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="c38d6-108">Birleştirilecek katmanlar.</span><span class="sxs-lookup"><span data-stu-id="c38d6-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="c38d6-109">Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="c38d6-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="c38d6-110">Diğer tüm katmanların birleştirilmesiyle temsil eden, tek bir kontrollü tek katman.</span><span class="sxs-lookup"><span data-stu-id="c38d6-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>