---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Measurewithkaralama işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854653"
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