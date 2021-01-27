---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853594"
---
# <a name="_assertequalonbasisvector-operation"></a>_assertEqualOnBasisVector işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


İki işlem `givenU` ve bir temel duruma uygulamanın sonucunun aynı olup olmadığını denetler `expectedU` . Temel durum, `basis` parametresiyle açıklanır.
<xref:microsoft.quantum.extensions.fliptobasis>Bu açıklama hakkında daha fazla bilgi için bkz. işlev.

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Giriş

### <a name="basis--int"></a>temel: [Int](xref:microsoft.quantum.lang-ref.int)[]

Her $n $ qubit için tek qubit tabanlı bir durum KIMLIĞI (0 <= kimlik <= 3) tarafından belirtilen temel durum.


### <a name="givenu--qubit--unit"></a>givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit) 

$N $ qubits üzerinde işlem denetlenecek.


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

GivenU 'nin karşılaştırılacağı $n $ qubits üzerinde başvuru işlemi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

