---
uid: Microsoft.Quantum.ErrorCorrection.Recover
title: Kurtarma işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: Recover
qsharp.summary: Performs a single round of error correction by a quantum code described by a `QECC` type.
ms.openlocfilehash: bdf09decc3705d3285f4eb605c176d7764a994d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200586"
---
# <a name="recover-operation"></a>Kurtarma işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tür tarafından tanımlanan bir hisse kodu tarafından hata düzeltmesinin tek bir yuvarlamesi gerçekleştirir `QECC` .

```qsharp
operation Recover (code : Microsoft.Quantum.ErrorCorrection.QECC, fn : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a>Giriş

### <a name="code--qecc"></a>kod: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Hisse hatası-bir tür olarak paketlenmiş kod düzeltme, `QECC` hisse verileri kodlamasını ve kodunu çözmeyi ve hata eşitleme 'nin nasıl ölçüldüğünü açıklar.


### <a name="fn--recoveryfn"></a>FN: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`Bu her bir hatayı, algılanan hatayı düzeltmek için her bir hata sendromu eşleyen `Pauli[]` işlemlere eşler.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Sabitleyici kodun tanımlandığı bir qubits dizisi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)
- [Microsoft. hisse. Errordüzeltmesini. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [Microsoft. hisse. Errordüzeltmesini. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)