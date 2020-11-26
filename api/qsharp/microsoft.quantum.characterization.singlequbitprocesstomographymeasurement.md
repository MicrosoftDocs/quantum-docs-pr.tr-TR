---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Singlequbitprocesstomographyıölçüm işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 3756040df8e34ecee1e968428b08387e0096ab7b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204207"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>Singlequbitprocesstomographyıölçüm işlemi

Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


, Belirli bir ilgi kanalı verildiğinde Pauli temelinde tek qubit işlem işlemleri gerçekleştirir.

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>Giriş

### <a name="preparation--pauli"></a>Hazırlık: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Bir qubit 'in hazırlanmakta olduğu Pauli temel öğesi $P $.


### <a name="measurement--pauli"></a>ölçüm: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Bir qubit 'in ölçülecek olan Pauli temel öğesi $Q.


### <a name="channel--qubit--unit"></a>Kanal: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Tek bir qubit kanalı $ \Lambda $, davranışları işlem turununile tahmin ediliyor.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

`Zero`Olasılığa sahip sonuç $ $ \begin{hizalaması} \Pr (\Texttt{dd} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\cıvadone + Q} {2} \Lambalo\left [\frac{\cıvadone + P} {2} \ sağ] \ sağ).
\end{hizalaması} $ $

## <a name="remarks"></a>Açıklamalar

Bu işlem tarafından döndürülen sonuçların üzerine dağıtım, iki-qubit durumu tomografi özel bir durumdur. $ \ Lambda $ için Choi – Jamiłkowski durumu $ \rho = J (\Lambda)/$2 olmalıdır. Daha sonra, yukarıdaki dağıtım $ $ \begin{hizalaması} \Pr (\Texttt{dd} | \rho; ile aynıdır. M) = \operatorname{Tr} (M \rho), \end{hizalaması} $ $ burada $M = 2 (\cıvadone + P) ^ \mathrm{T}/2 \cdot (\cıvadone + Q)/$2, $P $ ve $Q $ öğesine karşılık gelen etkili ölçümdür.