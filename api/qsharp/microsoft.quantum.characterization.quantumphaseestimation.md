---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Miktar Tumphasetahmin işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 7e524477a4b2bcd8d6767441e278fbf501355e0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728177"
---
# <a name="quantumphaseestimation-operation"></a>Miktar Tumphasetahmin işlemi

Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)

Leyebilir [](https://nuget.org/packages/)


Belirli bir Oracle `U` ve `targetState` aşamayı bir büyük endian hisse kaydına okumak için hisse aşaması tahmin algoritmasını gerçekleştirir.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Giriş

### <a name="oracle--discreteoracle"></a>Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Verilen tamsayı güçleri için $U ^ d $ uygulayan bir işlem.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{\phi} $ durumunu temsil eden bir hisse kaydı $U $ tarafından kullanılabilir. $ \Ket{\phi} $ bir $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \fi \ [0, 2 \ Pi) $ bilinmeyen bir aşama.


### <a name="controlregister--bigendian"></a>controlRegister: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Belirtilen Oracle 'ı denetlemek için kullanılabilen ve bu işlemin uygulamadan sonraki $ \phi $ gösterimini içeren büyük endian temsili tamsayı kaydı. ControlRegister 'ın, kayıt uzunluğunun istenen hassasiyetini gösterdiği ilk durum olan $ \ket{00\cnoktalar 0} $ başlangıç durumunda başlaması varsayılır.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

