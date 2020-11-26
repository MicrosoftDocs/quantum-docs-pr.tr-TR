---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 3e6774e2fe348668840cdc08fe3a070ec3d82a6d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216090"
---
# <a name="robustphaseestimation-operation"></a>RobustPhaseEstimation işlemi

Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


, Belirli bir Oracle ve eigenstate için dayanıklı ve dayanıklı olmayan dayanıklı bir tahmin algoritması gerçekleştirir `U` ve Heisenberg sınırında varyans ölçeklendirmesiyle aşamanın gerçek değerli tek bir tahminini sağlar.

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Giriş

### <a name="bitsprecision--int"></a>bitsPrecision: [Int](xref:microsoft.quantum.lang-ref.int)

Bu, $ \sigma \le 10,7 \pı/\Text{# sorgu} $ gibi birkaç sorgu ölçeklendirmesinin kullanıldığı standart sapma $ \sigma \ Le 2 \ pi/2 ^ \text{bitsPrecision} $ olan $ \phi $ tahminini sağlar.


### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Verilen tamsayı üsleri $m $ için $U ^ d $ uygulayan bir işlem.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$U $ ' nin üzerinde hareket eden bir hisse kaydı. Bu bir eigenstate $ \ket{\phi} $ of $U $, sonra $ \phi\in (-\pı, \pı] $ için bilinmeyen bir aşama olan \ket{\phi} = e ^ {i\phi} \ket{\phi} $ öğesini $U.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Açıklamalar

Çok sayıda sorgu sınırında, $ \phi $ ile ilgili $ \sigma \ GE 2 \pı/\Text{# sorgu} $ tahmininin standart sapması için alt sınır Cramer-Rao.

## <a name="references"></a>Başvurular

- Kımel, Guang Hao Low, Theodore J. Yoder tarafından sağlam aşama tahmini aracılığıyla bir evrensel Single-Qubit Gate-Set sağlam ayarı https://arxiv.org/abs/1502.02677