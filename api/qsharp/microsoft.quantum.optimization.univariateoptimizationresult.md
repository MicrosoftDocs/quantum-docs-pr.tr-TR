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
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. iyileştirmesi](xref:Microsoft.Quantum.Optimization)

Leyebilir [](https://nuget.org/packages/)


Bir tek değişkenli işlevi en iyi duruma getirme sonucunu temsil eder.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="coordinate--double"></a>Koordinat: [Double](xref:microsoft.quantum.lang-ref.double)

En iyi konumda bulunan giriş.
### <a name="value--double"></a>Değer: [Double](xref:microsoft.quantum.lang-ref.double)

İşlev tarafından en iyi şekilde döndürülen değer.