---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Pauliblockenkodlamaya işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848017"
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