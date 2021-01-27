---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: d7c8df079e49b2ce0a5106e430ef4060df85cdc4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825766"
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