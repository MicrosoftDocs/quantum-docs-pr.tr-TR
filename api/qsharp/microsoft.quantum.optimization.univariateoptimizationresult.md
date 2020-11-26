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
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. iyileştirmesi](xref:Microsoft.Quantum.Optimization)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tek değişkenli işlevi en iyi duruma getirme sonucunu temsil eder.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="coordinate--double"></a>Koordinat: [Double](xref:microsoft.quantum.lang-ref.double)

En iyi konumda bulunan giriş.
### <a name="value--double"></a>Değer: [Double](xref:microsoft.quantum.lang-ref.double)

İşlev tarafından en iyi şekilde döndürülen değer.