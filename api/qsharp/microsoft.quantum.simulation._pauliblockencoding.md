---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726341"
---
# <a name="_pauliblockencoding-function"></a>_PauliBlockEncoding işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Hamiltonian için blok kodlama Unitary oluşturur.

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $, her biri gerçek katsayı değeri $ \ $P $ olan Pauli terimlerinin toplamı ile açıklanmıştır _j $.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Giriş

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Pauli koşullarının toplamı olarak $H $ tanımlayan bir.


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a>stateprepunitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [littliendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama + CTL

$ \Ket{j} $ dizininde bulunan Unitary $V _j $ kontrollü bir işlev $f: j\tim Tarrow V_j $ olan Unitary işlemi $V $.


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a>Çoğullayıcı: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL)-> ([litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL





## <a name="output--doubleblockencodingreflection"></a>Çıkış: ([Double](xref:microsoft.quantum.lang-ref.double),[blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>İlk parametre

Katsayıların $ \alfa = \ sum_ {j} | \ alpha_j | $ sayısının bir normu.

## <a name="second-parameter"></a>İkinci parametre

`BlockEncodingReflection`Hamiltonian $U $ 'ın Unitary $U $. Bu Unitary, $U ^ 2 = I $ ile aynı zamanda bir yansıdır.

## <a name="remarks"></a>Açıklamalar

Örnek, $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ durumunu hazırlama ve hazırlamayı geri al ve çarpma denetimli bir Unitary oluşturma işlemlerini ve <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .