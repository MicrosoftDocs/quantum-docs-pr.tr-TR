---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis
title: AssertOperationsEqualInPlaceCompBasis işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlaceCompBasis
qsharp.summary: Checks if the operation `givenU` is equal to the operation `expectedU` on the given input size  by checking the action of the operations only on the vectors from the computational basis. This is a necessary, but not sufficient, condition for the equality of two unitaries.
ms.openlocfilehash: 826369bdf3544fb257c2bb202466426c1ca1e113
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202354"
---
# <a name="assertoperationsequalinplacecompbasis-operation"></a>AssertOperationsEqualInPlaceCompBasis işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


İşlemin `givenU` `expectedU` yalnızca işlem temelinde vektörlerdeki işlem eylemlerini denetleyerek verilen giriş boyutundaki işleme eşit olup olmadığını denetler.
Bu, iki unitı 'nin eşitliğine yönelik gerekli, ancak yeterli olmayan bir durumdur.

```qsharp
operation AssertOperationsEqualInPlaceCompBasis (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

İşlemler `givenU` ve üzerinde çalışan qubits $n $ sayısı `expectedU` .


### <a name="givenu--qubit--unit"></a>givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit) 

$N $ qubits üzerinde işlem denetlenecek.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

İle Karşılaştırılacak $n $ qubit üzerinde başvuru işlemi `givenU` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

