---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727320"
---
# <a name="assertphase-operation"></a>AssertPhase işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


Bir eşit üst konum durumunun beklenen değere sahip olduğunu onaylar.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Açıklama

Bu işlem, bazı rastgele gerçek $t $ için beklenen değere sahip $ \frac{e ^ {ı t}} {\sqrt {2} } (e ^ {i\phi} \ demet {0} + e ^ {-i\phi} \ ayraç {1} ) $ olarak ifade edilen bir hisse cısının $ \phi $ aşamasını onaylar

## <a name="input"></a>Giriş

### <a name="expected--double"></a>beklenen: [çift](xref:microsoft.quantum.lang-ref.double)

$ \Phi \ in (-\pı, \pı] $ değerinin beklenen değeri.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Beklenen durumu depolayan qubit.


### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Gerçek ve beklenen arasındaki fark için mutlak tolerans.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

