---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: 6c048c17df21d1026dc671f30d72a13ed8d8b7f5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200637"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir sabitleyici grubun verilen Oluşturucu kümesini ölçer.

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a>Giriş

### <a name="stabilizergroup--pauli"></a>Sabitde Izergrubu: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Multiqubit Pauli işleçleri dizisi.
Örneğin, `stabilizerGroup[0]` bir sabitleyici Oluşturucu olan Tensor ürünü olan tek qubit Pauli matrislerinin bir listesidir.


### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Sabitleyici kodun tanımlandığı bir qubits dizisi.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Araç: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __geçersiz <Result>__ 

Multiqubit Pauli işlecinin nasıl ölçülmesi gerektiğini belirten bir işlem.



## <a name="output--syndrome"></a>Çıkış: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Ölçümlerin sonucu.

## <a name="remarks"></a>Açıklamalar

Bu, verilen bir dizi kümesinin yürütülüyor olup olmadığını denetlemez.
Bunlar işlem yapılmadığından, ölçümlerin sonucu rastgele olabilir.