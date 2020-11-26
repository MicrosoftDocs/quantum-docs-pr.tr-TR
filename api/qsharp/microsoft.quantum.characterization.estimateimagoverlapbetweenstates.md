---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimateImagOverlapBetweenStates işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: b192abc4ba37d126bf46f94c66cb87fe3bbec4c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216209"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a>EstimateImagOverlapBetweenStates işlemi

Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Her birinin bir durum kopyasını hazırlayabileceği iki işlem, her bir işlem tarafından hazırlanan durumlar arasındaki çakışmadan oluşan sanal kısmını tahmin eder.

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>Giriş

### <a name="commonpreparation--qubit--unit--is-adj"></a>Commonhazırlama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Sabit bir giriş durumunu hazırlayan bir işlem.


### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Karşılaştırılacak iki durum hazırlık işlemi.


### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Karşılaştırılacak iki durum hazırlık işlemi saniyesi.


### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

`commonPreparation`, `preparation1` Ve hepsi üzerinde işlem gören qubit sayısı `preparation2` .


### <a name="nmeasurements--int"></a>Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)

Örtüşmeyi tahmin etmek için kullanılacak ölçüm sayısı.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Açıklamalar

Bu işlem, $ $ \begin{hizalaması} \braket{\psı | öğesinin sanal bölümünü bulmak için Hadamard testini kullanır V ^ {\ dağılım} U | \psı} \end{hizalaması} $ $; $ \ket{\psı} $, tarafından hazırlanan durumdur `commonPreparation` , $U $, ' nin eyleminin Unitary gösterimidir `preparation1` ve $V $ öğesinin karşılık geldiği yerdir `preparation2` .

## <a name="references"></a>Başvurular

- Aharonov *et al.* [Quant-pH/0511096](https://arxiv.org/abs/quant-ph/0511096).

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. karakterleştirme. EstimateRealOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [Microsoft. hisse. karakterleştirme. EstimateOverlapBetweenStates](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)