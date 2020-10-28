---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: Blochspburkoordinatları işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 6614b78c8e64c205cc94052cc64dd957814ab3d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733263"
---
# <a name="blochspherecoordinates-function"></a>Blochspburkoordinatları işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Leyebilir [](https://nuget.org/packages/)


Tek qubit durumu için Bloch Sphere koordinatlarını hesaplar.

Bu iki karmaşık sayı $a, qubit durumunu temsil eden 0, a1 $, $a 0 \ ayraç {0} + a1 \ {1} Tus= r e ^ {it} (e ^ {-ı \phi/2}\cos{(\ teta/2)} {0} \tus+ e ^ {ı \fi/2}\sin{(\ teta/2)} \ket {1} ) $.

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a>Giriş

### <a name="a0--complexpolar"></a>a0: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)

Karmaşık katsayı devleti $ \ket {0} $.


### <a name="a1--complexpolar"></a>a1: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)

Karmaşık katsayı devleti $ \ket {1} $.



## <a name="output--complexpolardoubledouble"></a>Çıkış: ([Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))

İçeren bir tanımlama grubu `(ComplexPolar(r, t), phi, theta)` .