---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727026"
---
# <a name="measurestabilizergenerators-operation"></a>MeasureStabilizerGenerators işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Leyebilir [](https://nuget.org/packages/)


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


### <a name="gadget--pauliqubit--__invalidresult__"></a>Araç: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __geçersiz <Result>__ 

Multiqubit Pauli işlecinin nasıl ölçülmesi gerektiğini belirten bir işlem.



## <a name="output--syndrome"></a>Çıkış: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Ölçümlerin sonucu.

## <a name="remarks"></a>Açıklamalar

Bu, verilen bir dizi kümesinin yürütülüyor olup olmadığını denetlemez.
Bunlar işlem yapılmadığından, ölçümlerin sonucu rastgele olabilir.