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
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="5c635-102">_PauliBlockEncoding işlevi</span><span class="sxs-lookup"><span data-stu-id="5c635-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="5c635-103">Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5c635-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5c635-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c635-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c635-105">Hamiltonian için blok kodlama Unitary oluşturur.</span><span class="sxs-lookup"><span data-stu-id="5c635-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="5c635-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $, her biri gerçek katsayı değeri $ \ $P $ olan Pauli terimlerinin toplamı ile açıklanmıştır _j $.</span><span class="sxs-lookup"><span data-stu-id="5c635-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="5c635-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="5c635-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="5c635-108">generatorSystem: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="5c635-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="5c635-109">`GeneratorSystem`Pauli koşullarının toplamı olarak $H $ tanımlayan bir.</span><span class="sxs-lookup"><span data-stu-id="5c635-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a><span data-ttu-id="5c635-110">stateprepunitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [littliendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama + CTL</span><span class="sxs-lookup"><span data-stu-id="5c635-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5c635-111">$ \Ket{j} $ dizininde bulunan Unitary $V _j $ kontrollü bir işlev $f: j\tim Tarrow V_j $ olan Unitary işlemi $V $.</span><span class="sxs-lookup"><span data-stu-id="5c635-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="5c635-112">Çoğullayıcı: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL)-> ([litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="5c635-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="5c635-113">Çıkış: ([Double](xref:microsoft.quantum.lang-ref.double),[blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="5c635-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="5c635-114">İlk parametre</span><span class="sxs-lookup"><span data-stu-id="5c635-114">First parameter</span></span>

<span data-ttu-id="5c635-115">Katsayıların $ \alfa = \ sum_ {j} | \ alpha_j | $ sayısının bir normu.</span><span class="sxs-lookup"><span data-stu-id="5c635-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="5c635-116">İkinci parametre</span><span class="sxs-lookup"><span data-stu-id="5c635-116">Second parameter</span></span>

<span data-ttu-id="5c635-117">`BlockEncodingReflection`Hamiltonian $U $ 'ın Unitary $U $.</span><span class="sxs-lookup"><span data-stu-id="5c635-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="5c635-118">Bu Unitary, $U ^ 2 = I $ ile aynı zamanda bir yansıdır.</span><span class="sxs-lookup"><span data-stu-id="5c635-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c635-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5c635-119">Remarks</span></span>

<span data-ttu-id="5c635-120">Örnek, $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ durumunu hazırlama ve hazırlamayı geri al ve çarpma denetimli bir Unitary oluşturma işlemlerini ve <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="5c635-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>