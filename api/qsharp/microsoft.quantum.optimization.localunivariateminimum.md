---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726492"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum işlevi

Ad alanı: [Microsoft. hisse. iyileştirmesi](xref:Microsoft.Quantum.Optimization)

Leyebilir [](https://nuget.org/packages/)


Bir tek değişkenli işlev için, altın Aralık araması kullanarak, bir ayırt eden değer için yerel minimum değeri döndürür.

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>Giriş

### <a name="fn--double---double"></a>FN: [çift](xref:microsoft.quantum.lang-ref.double) -> [çift](xref:microsoft.quantum.lang-ref.double)

Tek bir işlevin simge durumuna küçültülmesini sağlar.


### <a name="bounds--doubledouble"></a>sınırlar: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))

Yerel minimumın bulunduğu Aralık.


### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

İşlev girişi toleranslı olarak kullanılacak doğruluk.
Yerel opzma araması, aralığın genişliği bu toleranstan daha küçük olana kadar devam edecektir.



## <a name="output--univariateoptimizationresult"></a>Çıkış: [Univariateoptimizationresult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

Verilen sınırlar içinde bulunan, belirtilen işlevin yerel bir optimizasyonu.