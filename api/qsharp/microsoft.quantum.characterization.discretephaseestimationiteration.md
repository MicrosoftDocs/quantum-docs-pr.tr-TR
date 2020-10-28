---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 167b53d7108c64d11a4f258d17e90ba78d7dd8d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728231"
---
# <a name="discretephaseestimationiteration-operation"></a>DiscretePhaseEstimationIteration işlemi

Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)

Leyebilir [](https://nuget.org/packages/)


Bir Unitary Oracle 'ın tamsayı üslerini kullanarak yinelemeli (sınıflı kontrollü) bir aşama tahmin algoritmasının tek bir yinelemesini gerçekleştirir.

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit
```


## <a name="input"></a>Giriş

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

$U ^ d $, bir tamsayı ve bir yazmaç üzerinde işlem gören, burada $U $, aşaması tahmin edilecek olan Unitary, ve $m $, Oracle 'a verilen tamsayı gücüne sahip olduğu bir kayıt.


### <a name="power--int"></a>güç: [Int](xref:microsoft.quantum.lang-ref.int)

Verilen Unitary Oracle 'ın kaç kez uygulanacağını.


### <a name="theta--double"></a>Teta: [Double](xref:microsoft.quantum.lang-ref.double)

Hedef durum üzerinde işlem yapmadan önce denetim qubit üzerindeki aşamanın tersine çevirmek için kullanılacak açı.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Verilen Unitary Oracle tarafından üzerinde işlem yapılan durum kaydı.


### <a name="controlqubit--qubit"></a>controlQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Verilen Oracle 'ın uygulamasını denetlemek için kullanılan bir yardımcı qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

