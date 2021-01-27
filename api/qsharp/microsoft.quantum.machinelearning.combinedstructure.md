---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: b8ec007202c8e63dc2e98d0c752f6ba1a453e236
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847412"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="75ee3-102">CombinedStructure işlevi</span><span class="sxs-lookup"><span data-stu-id="75ee3-102">CombinedStructure function</span></span>

<span data-ttu-id="75ee3-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="75ee3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="75ee3-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="75ee3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="75ee3-105">Denetlenen bir veya daha fazla yönetim katmanı, farklı katmanlar ayrı model parametrelerine göre parametreleştirileyecek şekilde, model parametre dizini kaydırılan tek bir katman döndürür.</span><span class="sxs-lookup"><span data-stu-id="75ee3-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="75ee3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="75ee3-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="75ee3-107">katmanlar: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="75ee3-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="75ee3-108">Birleştirilecek katmanlar.</span><span class="sxs-lookup"><span data-stu-id="75ee3-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="75ee3-109">Çıkış: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="75ee3-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="75ee3-110">Diğer tüm katmanların birleştirilmesiyle temsil eden, tek bir kontrollü tek katman.</span><span class="sxs-lookup"><span data-stu-id="75ee3-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>

## <a name="example"></a><span data-ttu-id="75ee3-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="75ee3-111">Example</span></span>

<span data-ttu-id="75ee3-112">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="75ee3-112">The following are equivalent:</span></span>

```qsharp
let structure = CombinedStructure([
    LocalRotationLayer(2, PauliY),
    CyclicEntanglingLayer(3, PauliX, 2)
]);
let structure = [
    ControlledRotation((0, new Int[0]), PauliY, 0),
    ControlledRotation((1, new Int[0]), PauliY, 1),
    ControlledRotation((0, [2]), PauliX, 2),
    ControlledRotation((1, [0]), PauliX, 3),
    ControlledRotation((2, [1]), PauliX, 4)
];
```