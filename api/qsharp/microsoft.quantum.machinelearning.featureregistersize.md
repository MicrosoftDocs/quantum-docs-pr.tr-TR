---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196421"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="9af9d-102">FeatureRegisterSize işlevi</span><span class="sxs-lookup"><span data-stu-id="9af9d-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="9af9d-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9af9d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9af9d-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9af9d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="9af9d-105">Belirli bir özellik vektörünün kodlanması için gereken qubits sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="9af9d-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="9af9d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9af9d-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="9af9d-107">Örnek: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9af9d-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9af9d-108">Bir qubit kaydına kodlanacak örnek bir özellik vektörü.</span><span class="sxs-lookup"><span data-stu-id="9af9d-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="9af9d-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9af9d-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9af9d-110">Bir qubit kaydına kodlamak için gereken boyut `sample` , qubit sayısı olarak ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="9af9d-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>