---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830073"
---
# <a name="assertphase-operation"></a>AssertPhase işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir eşit üst konum durumunun beklenen değere sahip olduğunu onaylar.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Description

Bu işlem, bazı rastgele gerçek $t $ için beklenen değere sahip $ \frac{e ^ {ı t}} {\sqrt {2} } (e ^ {i\phi} \ demet {0} + e ^ {-i\phi} \ ayraç {1} ) $ olarak ifade edilen bir hisse cısının $ \phi $ aşamasını onaylar

## <a name="input"></a>Giriş

### <a name="expected--double"></a>beklenen: [çift](xref:microsoft.quantum.lang-ref.double)

$ \Phi \ in (-\pı, \pı] $ değerinin beklenen değeri.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Beklenen durumu depolayan qubit.


### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Gerçek ve beklenen arasındaki fark için mutlak tolerans.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

Şu onay başarılı oldu: `qubit` durum $ \ket{\psı} = e ^ {i 0,5} \ sqrt {1/2} \ demet {0} + e ^ {i 0,5} \ sqrt {1/2} \ demet {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` State $ \ket{\psı} = e ^ {i 0,5} \ sqrt {1/2} \ demet {0} + e ^ {-i 0,5} \ sqrt {1/2} \ demet {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` State $ \ket{\psı} = e ^ {-i 2.2} \ sqrt {1/2} \ {0} Tus+ e ^ {i 0.2} \ sqrt {1/2} \ demet {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`