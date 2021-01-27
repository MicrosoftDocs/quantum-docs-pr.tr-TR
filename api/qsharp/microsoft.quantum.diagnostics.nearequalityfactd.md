---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827903"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD işlevi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Klasik bir kayan nokta değerinin, 1e-10 ' un küçük bir toleransına kadar beklenen değere sahip olduğunu onaylar.

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>Giriş

### <a name="actual--double"></a>gerçek: [Double](xref:microsoft.quantum.lang-ref.double)

Denetlenecek sayı.


### <a name="expected--double"></a>beklenen: [çift](xref:microsoft.quantum.lang-ref.double)

Beklenen değer.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu, <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> $10 ^ $ sabit kodlanmış toleransı ile eşdeğerdir {-10} .