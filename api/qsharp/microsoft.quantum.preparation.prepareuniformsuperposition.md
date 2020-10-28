---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: Preparebirlik superposition işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725825"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="2fca8-102">Preparebirlik superposition işlemi</span><span class="sxs-lookup"><span data-stu-id="2fca8-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="2fca8-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="2fca8-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="2fca8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fca8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fca8-105">0 ile kodlayan durumlar üzerinde Tekdüzen üst konumu oluşturur `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="2fca8-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="2fca8-106">Diğer bir deyişle, bu Unitary $U $, $0 $ ile $M-$1 arasında tek bir üst konum oluşturarak bir giriş durumu $ \ket{0\cnoktalar 0} $ olarak sunulur.</span><span class="sxs-lookup"><span data-stu-id="2fca8-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="2fca8-107">Diğer bir deyişle, $ $ \begin{hizalaması} U\ket {0} = \frac {1} {\Sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="2fca8-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="2fca8-108">\end{hizalaması} $ $.</span><span class="sxs-lookup"><span data-stu-id="2fca8-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="2fca8-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="2fca8-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="2fca8-110">nDizinler: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2fca8-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2fca8-111">Tekdüzen üst konumunda istenen sayıda durum $M.</span><span class="sxs-lookup"><span data-stu-id="2fca8-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="2fca8-112">ındexregister: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2fca8-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2fca8-113">Sayı durumlarını depolayan qubit kaydı `LittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="2fca8-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="2fca8-114">Bu yazmaç $M-$1 numarasını depolayabilmelidir ve $ \ket{0\cnoktalar 0} $ durumunda başlatılmıştı.</span><span class="sxs-lookup"><span data-stu-id="2fca8-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fca8-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fca8-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2fca8-116">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2fca8-116">Remarks</span></span>

<span data-ttu-id="2fca8-117">İşlem adjointable ' dır, ancak söz konusu `indexRegister` durumda ilk temel durumlar üzerinde bir Tekdüzen üst konumunda olmasını gerektirir `nIndices` .</span><span class="sxs-lookup"><span data-stu-id="2fca8-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>