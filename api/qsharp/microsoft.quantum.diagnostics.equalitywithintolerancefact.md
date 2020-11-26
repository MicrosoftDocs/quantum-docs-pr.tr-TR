---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: Equalitywithıntoleranceolgu işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: 6ada2632974fddd6dd0fd8e4e6ab0866e4f29524
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201725"
---
# <a name="equalitywithintolerancefact-function"></a>Equalitywithıntoleranceolgu işlevi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir klasik kayan nokta değerinin, belirtilen mutlak tolerans için beklenen değere sahip olduğunu gösterir.

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>Giriş

### <a name="actual--double"></a>gerçek: [Double](xref:microsoft.quantum.lang-ref.double)

Denetlenecek sayı.


### <a name="expected--double"></a>beklenen: [çift](xref:microsoft.quantum.lang-ref.double)

Beklenen değer.


### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Gerçek ve beklenen arasındaki fark için mutlak tolerans.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

