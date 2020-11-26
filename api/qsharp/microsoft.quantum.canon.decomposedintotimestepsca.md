---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: aa5f09f2e1fde878b523b4efc20b86c26ac738ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216549"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="01f26-102">DecomposedIntoTimeStepsCA işlevi</span><span class="sxs-lookup"><span data-stu-id="01f26-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="01f26-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="01f26-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="01f26-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01f26-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="01f26-105">Belirli bir işlem için Trour – Suzuki tümleştirici uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="01f26-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="01f26-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="01f26-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="01f26-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01f26-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01f26-108">Zaman adımlarında kaldırılacak işlem sayısı.</span><span class="sxs-lookup"><span data-stu-id="01f26-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="01f26-109">Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="01f26-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="01f26-110">Ayrıştırma için bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü) kabul eden bir işlem `Double` .</span><span class="sxs-lookup"><span data-stu-id="01f26-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="01f26-111">Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01f26-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01f26-112">Kullanılacak Trour – Suzuki tümleştirici sırasını seçer.</span><span class="sxs-lookup"><span data-stu-id="01f26-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="01f26-113">Sipariş 1 ve hatta 2, 4, 6,... Şu anda destekleniyor.</span><span class="sxs-lookup"><span data-stu-id="01f26-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="01f26-114">Çıkış: ([çift](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="01f26-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="01f26-115">İlk parametrenin `Double` tümleştirme adımı boyutu olduğu ve ikinci parametrenin üzerinde işlem yapılma hedefi olan Trour – Suzuki tümleştirmesini uygulayan bir Unitary döndürür.</span><span class="sxs-lookup"><span data-stu-id="01f26-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="01f26-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="01f26-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01f26-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="01f26-117">'T</span></span>

<span data-ttu-id="01f26-118">Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="01f26-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="01f26-119">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="01f26-119">Remarks</span></span>

<span data-ttu-id="01f26-120">`order`Şuna eşit ile çağrıldığında `1` , bu işlev en düşük sıralı Baur – Suzuki tümleştirici $ $ \begin{hizalaması} s_1 (\lambda) = \ Prod_ {j = 1} ^ {m} e ^ {H_j \lambda} tarafından benzetilen bir işlem döndürür. \end{hizalaması} $ $ burada [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) ve Let $ \lambda $ 'ın bir evtime olması (döndürülen işlemin ilk girişi ile temsil edilir) ve izin ver $ \{ H_j \} _ {j = 1} ^ {m} $, " `op(j, lambda, _)` ^ {H_j \lambda} $ $e Unitary işleci tarafından benzetilen şekilde tümleştirildiği (skew-hermitian) dinamik.</span><span class="sxs-lookup"><span data-stu-id="01f26-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="01f26-121">Benzer şekilde, bir, `order` `2` ikinci sıra simetrik Trour – Suzuki tümleştirici $ $ \begin{hizalaması} S_2 (\lambda) = \ Prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ Prod_ {j ' = m} ^ {1} e ^ {h_ {j '} \lambda/2} döndürür.</span><span class="sxs-lookup"><span data-stu-id="01f26-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="01f26-122">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="01f26-122">\end{align} $$</span></span>

<span data-ttu-id="01f26-123">Daha yüksek değerler bile, `order` [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139)özyinelemeli yapımı kullanılarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="01f26-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="01f26-124">Başvurular</span><span class="sxs-lookup"><span data-stu-id="01f26-124">References</span></span>

- [<span data-ttu-id="01f26-125">*D. W. Braz, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="01f26-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)