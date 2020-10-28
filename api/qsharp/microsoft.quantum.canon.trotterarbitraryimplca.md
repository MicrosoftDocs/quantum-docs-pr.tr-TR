---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: Troempyönetiliyor Raryıımplca işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728322"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="13817-102">Troempyönetiliyor Raryıımplca işlemi</span><span class="sxs-lookup"><span data-stu-id="13817-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="13817-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="13817-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="13817-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13817-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13817-105">Çift sıralı Trour – Suzuki tümleştirici için yinelemeli uygulama.</span><span class="sxs-lookup"><span data-stu-id="13817-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="13817-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="13817-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="13817-107">sıra: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13817-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13817-108">Trotter-Suzuki tümleştirici sırası.</span><span class="sxs-lookup"><span data-stu-id="13817-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="13817-109">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13817-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13817-110">Zaman adımlarında kaldırılacak işlem sayısı.</span><span class="sxs-lookup"><span data-stu-id="13817-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="13817-111">Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="13817-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="13817-112">Bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü `Double` ) ve ayrıştırma için bir hisse kayıt (tür) kabul eden bir işlem `'T` .</span><span class="sxs-lookup"><span data-stu-id="13817-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="13817-113">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="13817-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="13817-114">Simülasyonun her adımının boyut çarpanı.</span><span class="sxs-lookup"><span data-stu-id="13817-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="13817-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="13817-115">target : 'T</span></span>

<span data-ttu-id="13817-116">İşlemlerin davranabileceği bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="13817-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="13817-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13817-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="13817-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="13817-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="13817-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="13817-119">'T</span></span>

<span data-ttu-id="13817-120">Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="13817-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>