---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854578"
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