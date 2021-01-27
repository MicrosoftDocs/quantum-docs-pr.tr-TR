---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Expandedkatsayıları işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835615"
---
# <a name="expandedcoefficients-function"></a>Expandedkatsayıları işlevi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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