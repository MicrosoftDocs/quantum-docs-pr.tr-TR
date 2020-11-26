---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5acfe5043342fd88276910a9fd0347f7d2f6960f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201521"
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