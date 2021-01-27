---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848435"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="9da33-102">FeatureRegisterSize işlevi</span><span class="sxs-lookup"><span data-stu-id="9da33-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="9da33-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9da33-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9da33-104">Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9da33-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="9da33-105">Belirli bir özellik vektörünün kodlanması için gereken qubits sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="9da33-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="9da33-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9da33-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="9da33-107">Örnek: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9da33-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9da33-108">Bir qubit kaydına kodlanacak örnek bir özellik vektörü.</span><span class="sxs-lookup"><span data-stu-id="9da33-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="9da33-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9da33-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9da33-110">Bir qubit kaydına kodlamak için gereken boyut `sample` , qubit sayısı olarak ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="9da33-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>