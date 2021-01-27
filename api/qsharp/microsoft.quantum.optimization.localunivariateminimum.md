---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854603"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum işlevi

Ad alanı: [Microsoft. hisse. iyileştirmesi](xref:Microsoft.Quantum.Optimization)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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