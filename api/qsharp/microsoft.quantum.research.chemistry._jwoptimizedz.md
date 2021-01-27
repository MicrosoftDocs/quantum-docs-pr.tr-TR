---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: _JWOptimizedZ işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 76c96153b6baf8b593e0770a44b6190c075c8f53
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854226"
---
# <a name="_jwoptimizedz-operation"></a>_JWOptimizedZ işlemi

Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Bir RZ dönüşü uygular ve bu, aşama tahminiyle birlikte çift aşamaya sahip.

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="angle--double"></a>açı: [Double](xref:microsoft.quantum.lang-ref.double)

RZ dönüşünün açısı.


### <a name="parityqubit--qubit"></a>parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Zaman evrimi 'nin işaretini belirleyen qubit.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

