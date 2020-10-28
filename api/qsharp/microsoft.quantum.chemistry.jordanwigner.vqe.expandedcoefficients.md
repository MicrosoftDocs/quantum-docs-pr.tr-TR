---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Expandedkatsayıları işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727649"
---
# <a name="expandedcoefficients-function"></a>Expandedkatsayıları işlevi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Leyebilir [](https://nuget.org/packages/)


Bu ve Pauli terimleri arasında bire bir eşleme elde etmek için Jordan-Wigner katsayısının Compact gösterimini genişletir.

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>Giriş

### <a name="coeff--double"></a>Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]

Jordan-Wigner Hamiltonian veri yapısından okunan bir dizi katsayısıdır.


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)

Jordan-Wigner teriminin türü.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)[]

Her Pauli dönemi için bir adet genişletilmiş katsayıların dizileri.