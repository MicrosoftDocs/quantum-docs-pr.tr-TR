---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Pauliblockenkodlamaya işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: b1df6d239e6ef061cf0a4784c652e9dd126991d5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230438"
---
# <a name="pauliblockencoding-function"></a>Pauliblockenkodlamaya işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hamiltonian için blok kodlama Unitary oluşturur.

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $, her biri gerçek katsayı değeri $ \ $P $ olan Pauli terimlerinin toplamı ile açıklanmıştır _j $.

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Giriş

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Pauli koşullarının toplamı olarak $H $ tanımlayan bir.



## <a name="output--doubleblockencodingreflection"></a>Çıkış: ([Double](xref:microsoft.quantum.lang-ref.double),[blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>İlk parametre

Katsayıların $ \alfa = \ sum_ {j} | \ alpha_j | $ sayısının bir normu.

## <a name="second-parameter"></a>İkinci parametre

`BlockEncodingReflection`Hamiltonian $H $ 'ın Unitary $U $. Bu Unitary, $U ^ 2 = I $ ile aynı zamanda bir yansıdır.

## <a name="remarks"></a>Açıklamalar

Bu, $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ durumunun hazırlanması ve hazırlanması ve çarpma kontrollü bir Unitary ve oluşturma yoluyla elde edilir <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .