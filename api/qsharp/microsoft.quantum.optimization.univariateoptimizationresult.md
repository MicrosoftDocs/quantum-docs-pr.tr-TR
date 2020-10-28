---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733402"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="98c25-102">UnivariateOptimizationResult Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="98c25-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="98c25-103">Ad alanı: [Microsoft. hisse. iyileştirmesi](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="98c25-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="98c25-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="98c25-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="98c25-105">Bir tek değişkenli işlevi en iyi duruma getirme sonucunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="98c25-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="98c25-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="98c25-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="98c25-107">Koordinat: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="98c25-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="98c25-108">En iyi konumda bulunan giriş.</span><span class="sxs-lookup"><span data-stu-id="98c25-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="98c25-109">Değer: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="98c25-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="98c25-110">İşlev tarafından en iyi şekilde döndürülen değer.</span><span class="sxs-lookup"><span data-stu-id="98c25-110">Value returned by the function at its optimum.</span></span>