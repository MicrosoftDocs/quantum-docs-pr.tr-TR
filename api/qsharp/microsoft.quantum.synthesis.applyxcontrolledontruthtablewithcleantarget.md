---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Applyxcontroltadontruthtablewithcleantarget işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203272"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>Applyxcontroltadontruthtablewithcleantarget işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


@"microsoft.quantum.intrinsic.x" `target` `func` İçindeki klasik atama için Boolean işlevi true olarak değerlendirilirse, işlemini üzerine uygular `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bu işlem @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , hedef qubitin $ \ket $ durumunda olduğu bilinen özel durumunu uygular {0} .

Uygulama ve kapıları kullanımını sağlar @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" .  Adjoint işleminin uygulanması en iyi duruma getirilmiştir ve ölçüm tabanlı kaldırma işlemini kullanır.

## <a name="input"></a>Giriş

### <a name="func--bigint"></a>Func: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Büyük tamsayı olarak temsil edilen Boolean Truth tablosu


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Denetim qubits 'i kaydetme


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Hedef qubit ($ \ket {0} $ durumunda olmalıdır)



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Sensıs. Applyxcontroltadontruthtable](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)