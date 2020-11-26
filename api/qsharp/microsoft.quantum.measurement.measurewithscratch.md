---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Measurewithkaralama işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: c42316a811e0e4a81c7f244c093a2be88fe5c733
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227072"
---
# <a name="measurewithscratch-operation"></a>Measurewithkaralama işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ölçüyü gerçekleştirmek için açık bir karalama qubit kullanarak verilen Pauli işlecini ölçer.

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>Giriş

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tek qubit Pauli işleçleri dizisi olarak belirtilen bir multi-qubit Pauli işleci.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ölçülecek qubit kayıt.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__

Kayıttaki verilen Pauli işlecinin ölçüme sonucu `target` .