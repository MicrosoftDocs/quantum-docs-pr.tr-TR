---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728772"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="5d2f8-102">DecomposedIntoTimeStepsCA işlevi</span><span class="sxs-lookup"><span data-stu-id="5d2f8-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="5d2f8-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5d2f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5d2f8-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d2f8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d2f8-105">Belirli bir işlem için Trour – Suzuki tümleştirici uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="5d2f8-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="5d2f8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5d2f8-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="5d2f8-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d2f8-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d2f8-108">Zaman adımlarında kaldırılacak işlem sayısı.</span><span class="sxs-lookup"><span data-stu-id="5d2f8-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="5d2f8-109">Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="5d2f8-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5d2f8-110">Ayrıştırma için bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü) kabul eden bir işlem `Double` .</span><span class="sxs-lookup"><span data-stu-id="5d2f8-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="5d2f8-111">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d2f8-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d2f8-112">Kullanılacak Trour – Suzuki tümleştirici sırasını seçer.</span><span class="sxs-lookup"><span data-stu-id="5d2f8-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="5d2f8-113">Sipariş 1 ve hatta 2, 4, 6,... Şu anda destekleniyor.</span><span class="sxs-lookup"><span data-stu-id="5d2f8-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="5d2f8-114">Çıkış: ([çift](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="5d2f8-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5d2f8-115">İlk parametrenin `Double` tümleştirme adımı boyutu olduğu ve ikinci parametrenin üzerinde işlem yapılma hedefi olan Trour – Suzuki tümleştirmesini uygulayan bir Unitary döndürür.</span><span class="sxs-lookup"><span data-stu-id="5d2f8-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5d2f8-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="5d2f8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5d2f8-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="5d2f8-117">'T</span></span>

<span data-ttu-id="5d2f8-118">Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="5d2f8-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5d2f8-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5d2f8-119">Remarks</span></span>

<span data-ttu-id="5d2f8-120">`order`Şuna eşit ile çağrıldığında `1` , bu işlev en düşük sıralı Baur – Suzuki tümleştirici $ $ \begin{hizalaması} s_1 (\lambda) = \ Prod_ {j = 1} ^ {m} e ^ {H_j \lambda} tarafından benzetilen bir işlem döndürür. \end{hizalaması} $ $ burada [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) ve Let $ \lambda $ 'ın bir evtime olması (döndürülen işlemin ilk girişi ile temsil edilir) ve izin ver $ \{ H_j \} _ {j = 1} ^ {m} $, " `op(j, lambda, _)` ^ {H_j \lambda} $ $e Unitary işleci tarafından benzetilen şekilde tümleştirildiği (skew-hermitian) dinamik.</span><span class="sxs-lookup"><span data-stu-id="5d2f8-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="5d2f8-121">Benzer şekilde, bir, `order` `2` ikinci sıra simetrik Trour – Suzuki tümleştirici $ $ \begin{hizalaması} S_2 (\lambda) = \ Prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ Prod_ {j ' = m} ^ {1} e ^ {h_ {j '} \lambda/2} döndürür.</span><span class="sxs-lookup"><span data-stu-id="5d2f8-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="5d2f8-122">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="5d2f8-122">\end{align} $$</span></span>

<span data-ttu-id="5d2f8-123">Daha yüksek değerler bile, `order` [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139)özyinelemeli yapımı kullanılarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="5d2f8-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="5d2f8-124">Referanslar</span><span class="sxs-lookup"><span data-stu-id="5d2f8-124">References</span></span>

- [<span data-ttu-id="5d2f8-125">*D. W. Braz, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="5d2f8-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)