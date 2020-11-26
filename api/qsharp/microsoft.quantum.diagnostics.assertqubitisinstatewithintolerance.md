---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Assertqubitişsınstatewithıntoleransınıntoleransı işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 1ceb7243cba93e42c67cc3655283a5d07c96863e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202218"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="e5b6a-102">Assertqubitişsınstatewithıntoleransınıntoleransı işlemi</span><span class="sxs-lookup"><span data-stu-id="e5b6a-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="e5b6a-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e5b6a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e5b6a-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e5b6a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e5b6a-105">Beklenen durumda bir qubitin olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="e5b6a-106">`expected` karmaşık bir vektörü temsil eder, $ \ket{\psı} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="e5b6a-107">$A $, $b $ her birini temsil eden başlıkların ilk öğesi, karmaşık sayının gerçek bölümüdür; ikinci tane ise sanal parçadır.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="e5b6a-108">Son bağımsız değişken, onaylama işlemi yapılan toleransı tanımlar.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="e5b6a-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="e5b6a-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="e5b6a-110">beklenen: ([karmaşık](xref:Microsoft.Quantum.Math.Complex),[karmaşık](xref:Microsoft.Quantum.Math.Complex))</span><span class="sxs-lookup"><span data-stu-id="e5b6a-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="e5b6a-111">Sırasıyla $ \ket {0} $ ve $ \ket $ için karmaşık yükseltilmiş tudes bekleniyordu {1} .</span><span class="sxs-lookup"><span data-stu-id="e5b6a-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="e5b6a-112">kaydolun: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e5b6a-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e5b6a-113">Durumu belirtilmelidir.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="e5b6a-114">Bu qubitin diğer ayrılmış qubits 'lerden ayrılabilir olduğunu ve ayrılmadığını unutmayın.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="e5b6a-115">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5b6a-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e5b6a-116">Gerçek artırlale, beklenmeden sapmasına izin verilen ek tolerans.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="e5b6a-117">Ayrıntılar için aşağıdaki açıklamalara bakın.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e5b6a-118">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5b6a-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e5b6a-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="e5b6a-119">Remarks</span></span>

<span data-ttu-id="e5b6a-120">Aşağıdaki matematiksel matika kodu mi?, MX, My, MZ için ifadeleri doğrulamak için kullanılabilir:</span><span class="sxs-lookup"><span data-stu-id="e5b6a-120">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="e5b6a-121">Tolerans, \_ $ \langta\psi | \psı\rangle = x 1 I + x 2 x + x 3 Y + x 4 Z $ ve gerçek vektör (Y ₂) tarafından tanımlanan 3 boyutlu gerçek vektör (x ₂, x ₃, x ₄) arasındaki {\infty} $ uzaklığın $L. \_ \_ \_ \_ y ₃, y ₄), ρ = Y ₁ I + y ₂ x + y ₃ Y + y ₄ Z tarafından tanımlanır. burada ρ, kaydın durumuna karşılık gelen yoğunluk matrisi.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-121">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="e5b6a-122">Bu yalnızca, tr (ρ) ve tr (| ψ ⟩ ⟨ ψ |) öğelerinin hem 1 hem de (örn. x ₁ = 1/2, y ₁ = 1/2) olduğu varsayımıyla geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-122">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="e5b6a-123">Bu durum söz konusu değilse, işlev (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) ve (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) arasındaki l ∞ Distance 'ın tolerans parametresinden daha az olduğunu onaylar.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-123">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>