---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: Defaulttraıningoptions işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856002"
---
# <a name="defaulttrainingoptions-function"></a><span data-ttu-id="71f46-102">Defaulttraıningoptions işlevi</span><span class="sxs-lookup"><span data-stu-id="71f46-102">DefaultTrainingOptions function</span></span>

<span data-ttu-id="71f46-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="71f46-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="71f46-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="71f46-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="71f46-105">Eğitim sınıflandırıcıları için varsayılan seçenek kümesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="71f46-105">Returns a default set of options for training classifiers.</span></span>

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a><span data-ttu-id="71f46-106">Çıkış: [Traıningoptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="71f46-106">Output : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="71f46-107">Sınıflandırıcılardaki eğitim sırasında kullanılmak üzere makul bir varsayılan eğitim seçenekleri kümesi.</span><span class="sxs-lookup"><span data-stu-id="71f46-107">A reasonable set of default training options for use when training classifiers.</span></span>

## <a name="example"></a><span data-ttu-id="71f46-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="71f46-108">Example</span></span>

<span data-ttu-id="71f46-109">Varsayılan seçenekleri kullanmak için, ancak ek ölçümler ile `w/` işlecini kullanın:</span><span class="sxs-lookup"><span data-stu-id="71f46-109">To use the default options, but with additional measurements, use the `w/` operator:</span></span>

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```