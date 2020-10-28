---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Measurewithkaralama işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730986"
---
# <a name="measurewithscratch-operation"></a>Measurewithkaralama işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Leyebilir [](https://nuget.org/packages/)


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