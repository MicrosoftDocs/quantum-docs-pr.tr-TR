---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Pauliblockenkodlamaya işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730914"
---
# <a name="pauliblockencoding-function"></a>Pauliblockenkodlamaya işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


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