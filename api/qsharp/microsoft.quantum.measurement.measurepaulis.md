---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853779"
---
# <a name="measurepaulis-operation"></a>MeasurePaulis işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Multi-qubitpauli işleçleri dizisi verildiğinde, her birini belirtilen ölçüm aracını kullanarak ölçer ve sonra sonuçların dizisini döndürür.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Giriş

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Ölçülecek Multi-qubit Pauli işleçleri dizisi.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Verilen operatörlerin ölçülmesi için kaydolun.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Araç: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __geçersiz <Result>__ 

Verilen bir multi-qubit işlecinin ölçüsünü gerçekleştiren işlem.



## <a name="output--__invalidresult__"></a>Çıkış: __geçersiz <Result>__[]

Her öğesinin ' de bir öğelerinin ölçüden elde edilen sonuçları dizisi `paulis` `target` .