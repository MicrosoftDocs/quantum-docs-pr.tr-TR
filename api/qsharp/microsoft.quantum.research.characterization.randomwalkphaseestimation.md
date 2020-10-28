---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: Randomwalkphasetahmine işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726432"
---
# <a name="randomwalkphaseestimation-operation"></a>Randomwalkphasetahmine işlemi

Ad alanı: [Microsoft. hisse. araştırma. karakterleştirme](xref:Microsoft.Quantum.Research.Characterization)

Leyebilir [](https://nuget.org/packages/)


Belirli bir Oracle ve eigenstate 'teki klasik ölçüm sonuçlarında Bayeduyma çıkarımı için rastgele bir adım kullanarak yinelemeli aşama tahmini gerçekleştirir.

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Giriş

### <a name="initialmean--double"></a>ınitialortalama: [Double](xref:microsoft.quantum.lang-ref.double)

$ \Phi $ üzerinden ilk normal önceki dağıtım ortalaması.


### <a name="initialstddev--double"></a>ınitialstddev: [Double](xref:microsoft.quantum.lang-ref.double)

$ \Phi $ üzerinden ilk normal önceki dağıtımın standart sapması.


### <a name="nmeasurements--int"></a>Nölçümler: [Int](xref:microsoft.quantum.lang-ref.int)

Son posterior tahmine kabul edilecek ölçüm sayısı.


### <a name="maxmeasurements--int"></a>Maxölçüler: [Int](xref:microsoft.quantum.lang-ref.int)

İşlemin başarısız olduğu kabul edilmeden önce alınabilecek toplam ölçüm sayısı.


### <a name="unwind--int"></a>geriye doğru izleme: [Int](xref:microsoft.quantum.lang-ref.int)

Tutarlılık denetimi başarısız olduğunda unutmak için sonuç sayısı.


### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Bir Unitary $U $ öğesini temsil eden bir işlem, $U (t) \ket{\phi} = e ^ {ı t \phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $ için bilinmeyen aşama $ \phi \ \mathbb{R} ^ + $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$U $ üzerinde hareket eden bir kayıt.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

Son tahmin $ \hat{\phi} \mathrel{: =} \beklediği [\phi] $, burada beklenmenin, kabul edilen tüm veriler verildiğinde posterior üzerinde olduğu.

## <a name="remarks"></a>Açıklamalar

### <a name="iterative-phase-estimation-and-eigenstates"></a>Yinelemeli aşama tahmini ve Eigenstates

Genel olarak, giriş kaydının `eigenstate` bir eigenstate $ \ket{\phi} $ $U $ olması gerekmez, ancak eigenstates üzerinde bir üst konum olabilir. Giriş durumunun \begin{hizalaması} \ket{\psı} & = \sum \_ {j} \Alpha \_ j \ket{\phi j} tarafından verildiğini varsayalım. \_ \end{hizalaması}; $ \{ \Alpha j \_ \} $, $ \sum \_ j | \alpha \_ j | ^ 2 = $1 ve $U \ket{\phi \_ j} = \phi \_ j\tus{\ Phi \_ j} $ gibi karmaşık katlardır.

Daha sonra, yinelemeli aşama tahmini gerçekleştirmek [geliştirme kılavuzunda](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)açıklandığı gibi, sonunda tek bir eigenstate 'e yakınsayacaktır.

### <a name="experiment-design"></a>Deneme tasarımı

$T $ ve Inversion açıları $ \teta $ öğesine geçirilen ölçüm süreleri `oracle` , *parçacık tahmin buluşsal* yöntemi, \begin{hizalaması} \teta \ sim \pr (\fi), \dörtlü t \yaklaşık \frac {1} {\variance{\phi}} öğesine göre seçilir.
\end{hizalaması} bu buluşsal yöntemi, daha önce normal varsayımıyla, yinelemeli aşama tahminlerinde beklenen posterior varyansı azaltmak için idealdir.

### <a name="optimality"></a>Optimizasyonu

Bu işlem, ikinci dereceden kayıp $L (\fi, \hat{\phi}) \mathrel{: =} (\fi-\hat{\phi}) ^ 2 $ olarak değerlendirilen $ \phi $ aşaması için en uygun tahmin aracı 'a yaklaştırır.

Yinelemeli aşama tahmini istatistikleri hakkında daha fazla bilgi için bkz. [Bayeme aşaması tahmini](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) .

## <a name="references"></a>Referanslar

- Ferrie *et al.* 2011 [DOI: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [arxıv: 1110.3067](https://arxiv.org/abs/1110.3067).
- Wiebe *et al.* 2013 [DOI: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [arxıv: 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe ve granade 2018 *(hazırlık aşamasında)* .