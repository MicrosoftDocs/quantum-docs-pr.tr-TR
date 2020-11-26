---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194041"
---
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="868ab-102">UnivariateOptimizationResult Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="868ab-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="868ab-103">Ad alanı: [Microsoft. hisse. iyileştirmesi](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="868ab-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="868ab-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="868ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="868ab-105">Bir tek değişkenli işlevi en iyi duruma getirme sonucunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="868ab-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="868ab-106">Adlandırılmış öğeler</span><span class="sxs-lookup"><span data-stu-id="868ab-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="868ab-107">Koordinat: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="868ab-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="868ab-108">En iyi konumda bulunan giriş.</span><span class="sxs-lookup"><span data-stu-id="868ab-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="868ab-109">Değer: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="868ab-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="868ab-110">İşlev tarafından en iyi şekilde döndürülen değer.</span><span class="sxs-lookup"><span data-stu-id="868ab-110">Value returned by the function at its optimum.</span></span>