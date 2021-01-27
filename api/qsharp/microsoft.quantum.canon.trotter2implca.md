---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 34b60934b67c19b2d1d718d68b85a2f0fffeab5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852029"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="6ba37-102">Trotter2ImplCA işlemi</span><span class="sxs-lookup"><span data-stu-id="6ba37-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="6ba37-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6ba37-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6ba37-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ba37-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ba37-105">İkinci sipariş rahatlığını – Suzuki tümleştirici uygulama.</span><span class="sxs-lookup"><span data-stu-id="6ba37-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6ba37-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6ba37-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="6ba37-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ba37-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ba37-108">Zaman adımlarında kaldırılacak işlem sayısı.</span><span class="sxs-lookup"><span data-stu-id="6ba37-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="6ba37-109">Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="6ba37-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6ba37-110">Bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü `Double` ) ve ayrıştırma için bir hisse kayıt (tür) kabul eden bir işlem `'T` .</span><span class="sxs-lookup"><span data-stu-id="6ba37-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="6ba37-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6ba37-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6ba37-112">Simülasyonun her adımının boyut çarpanı.</span><span class="sxs-lookup"><span data-stu-id="6ba37-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="6ba37-113">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="6ba37-113">target : 'T</span></span>

<span data-ttu-id="6ba37-114">İşlemlerin davranabileceği bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="6ba37-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6ba37-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6ba37-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6ba37-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6ba37-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6ba37-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6ba37-117">'T</span></span>

<span data-ttu-id="6ba37-118">Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="6ba37-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="6ba37-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="6ba37-119">Example</span></span>

<span data-ttu-id="6ba37-120">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="6ba37-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(0, deltaT / 2.0, target);
```

<span data-ttu-id="6ba37-121">ve</span><span class="sxs-lookup"><span data-stu-id="6ba37-121">and</span></span>

```qsharp
Trotter2ImplCA((2, op), deltaT, target);
```