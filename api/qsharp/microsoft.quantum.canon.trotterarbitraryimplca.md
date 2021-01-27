---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Troempyönetiliyor Raryıımplca işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: bb93517a479ce344277bfe97d070e6630a8fccc0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840092"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="28ad3-102">Troempyönetiliyor Raryıımplca işlemi</span><span class="sxs-lookup"><span data-stu-id="28ad3-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="28ad3-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28ad3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28ad3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28ad3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28ad3-105">Çift sıralı Trour – Suzuki tümleştirici için yinelemeli uygulama.</span><span class="sxs-lookup"><span data-stu-id="28ad3-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="28ad3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="28ad3-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="28ad3-107">sıra: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28ad3-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28ad3-108">Trotter-Suzuki tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="28ad3-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="28ad3-109">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="28ad3-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="28ad3-110">Zaman adımlarında kaldırılacak işlem sayısı.</span><span class="sxs-lookup"><span data-stu-id="28ad3-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="28ad3-111">Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="28ad3-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="28ad3-112">Bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü `Double` ) ve ayrıştırma için bir hisse kayıt (tür) kabul eden bir işlem `'T` .</span><span class="sxs-lookup"><span data-stu-id="28ad3-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="28ad3-113">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="28ad3-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="28ad3-114">Simülasyonun her adımının boyut çarpanı.</span><span class="sxs-lookup"><span data-stu-id="28ad3-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="28ad3-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="28ad3-115">target : 'T</span></span>

<span data-ttu-id="28ad3-116">İşlemlerin davranabileceği bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="28ad3-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28ad3-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28ad3-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="28ad3-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="28ad3-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28ad3-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="28ad3-119">'T</span></span>

<span data-ttu-id="28ad3-120">Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="28ad3-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>