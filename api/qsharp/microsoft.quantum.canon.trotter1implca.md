---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Trotter1ImplCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 6de4b6e7a34d66037d83a6e2bd5821402207c743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840114"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="fcb54-102">Trotter1ImplCA işlemi</span><span class="sxs-lookup"><span data-stu-id="fcb54-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="fcb54-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fcb54-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fcb54-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fcb54-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fcb54-105">İlk sipariş rahatlığını – Suzuki tümleştirici uygulama.</span><span class="sxs-lookup"><span data-stu-id="fcb54-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fcb54-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fcb54-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="fcb54-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fcb54-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fcb54-108">Zaman adımlarında kaldırılacak işlem sayısı.</span><span class="sxs-lookup"><span data-stu-id="fcb54-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="fcb54-109">Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="fcb54-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="fcb54-110">Bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü `Double` ) ve ayrıştırma için bir hisse kayıt (tür) kabul eden bir işlem `'T` .</span><span class="sxs-lookup"><span data-stu-id="fcb54-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="fcb54-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fcb54-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fcb54-112">Simülasyonun her adımının boyut çarpanı.</span><span class="sxs-lookup"><span data-stu-id="fcb54-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="fcb54-113">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="fcb54-113">target : 'T</span></span>

<span data-ttu-id="fcb54-114">İşlemlerin davranabileceği bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="fcb54-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fcb54-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fcb54-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fcb54-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="fcb54-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fcb54-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="fcb54-117">'T</span></span>

<span data-ttu-id="fcb54-118">Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="fcb54-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="fcb54-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="fcb54-119">Example</span></span>

<span data-ttu-id="fcb54-120">Aşağıdakiler eşdeğerdir:</span><span class="sxs-lookup"><span data-stu-id="fcb54-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT, target);
op(1, deltaT, target);
```

<span data-ttu-id="fcb54-121">ve</span><span class="sxs-lookup"><span data-stu-id="fcb54-121">and</span></span>

```qsharp
Trotter1ImplCA((2, op), deltaT, target);
```