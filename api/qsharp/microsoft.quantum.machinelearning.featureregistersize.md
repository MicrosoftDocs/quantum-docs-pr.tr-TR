---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732810"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="ced90-102">FeatureRegisterSize işlevi</span><span class="sxs-lookup"><span data-stu-id="ced90-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="ced90-103">Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ced90-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ced90-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ced90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ced90-105">Belirli bir özellik vektörünün kodlanması için gereken qubits sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="ced90-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="ced90-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ced90-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="ced90-107">Örnek: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ced90-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ced90-108">Bir qubit kaydına kodlanacak örnek bir özellik vektörü.</span><span class="sxs-lookup"><span data-stu-id="ced90-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="ced90-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ced90-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ced90-110">Bir qubit kaydına kodlamak için gereken boyut `sample` , qubit sayısı olarak ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="ced90-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>