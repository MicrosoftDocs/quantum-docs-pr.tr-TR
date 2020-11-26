---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 30b21a8e86eb5a4dd8dd8207dbdc6a0970308319
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216260"
---
# <a name="estimatefrequency-operation"></a>EstimateFrequency işlemi

Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hazırlık ve ölçüm verildiğinde, `Zero` belirli bir deneme sayısı gerçekleştirerek, ölçümün başarılı olduğu sıklığı (döndürür) tahmin eder.

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Giriş

### <a name="preparation--qubit--unit"></a>Hazırlık: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) 

Giriş kaydı üzerinde verilen bir durum $ \rho $ hazırlayan bir işlem $P $.


### <a name="measurement--qubit--__invalidresult__"></a>ölçüm: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __geçersiz <Result>__ 

Bir işlem, ilgilendiğiniz ölçümü temsil eden $M.


### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Her birinin hazırlanması ve ölçüsünün işlem yapması gereken qubit sayısı.


### <a name="nmeasurements--int"></a>Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)

İlgilendiğiniz sıklığı tahmin etmek için ölçümün kaç kez gerçekleştirilmesi gerektiği.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

$M sıklığı (p (\ket{00 \ cnoktalar 0} \bra{00 \ cnoktalar 0})) $ işlevinin tahmini bir $ \hat{p} $ `Zero` \_ \_ $n \_ {\upoklu} $, gözlenen sonuçların sayısıdır ve bu, {\upoklu} $, gözlenmemiş binom tahmin aracı $ \hat{p} = n {\upoklu}/n {\Text{measurements}} $ kullanılarak elde edilir `Zero` .

Bu, olasılıkların ölçülemez olması gibi fiziksel sınırlamalara yönelik hedef makinelerde özellikle önemlidir.