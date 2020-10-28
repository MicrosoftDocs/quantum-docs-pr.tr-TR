---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731114"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="97fd2-102">CombinedStructure işlevi</span><span class="sxs-lookup"><span data-stu-id="97fd2-102">CombinedStructure function</span></span>

<span data-ttu-id="97fd2-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="97fd2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="97fd2-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97fd2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97fd2-105">Denetlenen bir veya daha fazla yönetim katmanı, farklı katmanlar ayrı model parametrelerine göre parametreleştirileyecek şekilde, model parametre dizini kaydırılan tek bir katman döndürür.</span><span class="sxs-lookup"><span data-stu-id="97fd2-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="97fd2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="97fd2-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="97fd2-107">katmanlar: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="97fd2-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="97fd2-108">Birleştirilecek katmanlar.</span><span class="sxs-lookup"><span data-stu-id="97fd2-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="97fd2-109">Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="97fd2-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="97fd2-110">Diğer tüm katmanların birleştirilmesiyle temsil eden, tek bir kontrollü tek katman.</span><span class="sxs-lookup"><span data-stu-id="97fd2-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>