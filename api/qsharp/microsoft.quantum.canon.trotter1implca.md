---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Trotter1ImplCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1b4e0a9597f4f30b8e92ef91ff0780e7c7ecdc9b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204802"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="d76e2-102">Trotter1ImplCA işlemi</span><span class="sxs-lookup"><span data-stu-id="d76e2-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="d76e2-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d76e2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d76e2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d76e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d76e2-105">İlk sipariş rahatlığını – Suzuki tümleştirici uygulama.</span><span class="sxs-lookup"><span data-stu-id="d76e2-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d76e2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d76e2-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="d76e2-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d76e2-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d76e2-108">Zaman adımlarında kaldırılacak işlem sayısı.</span><span class="sxs-lookup"><span data-stu-id="d76e2-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="d76e2-109">Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="d76e2-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d76e2-110">Bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü `Double` ) ve ayrıştırma için bir hisse kayıt (tür) kabul eden bir işlem `'T` .</span><span class="sxs-lookup"><span data-stu-id="d76e2-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="d76e2-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d76e2-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d76e2-112">Simülasyonun her adımının boyut çarpanı.</span><span class="sxs-lookup"><span data-stu-id="d76e2-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="d76e2-113">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="d76e2-113">target : 'T</span></span>

<span data-ttu-id="d76e2-114">İşlemlerin davranabileceği bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="d76e2-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d76e2-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d76e2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d76e2-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="d76e2-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d76e2-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="d76e2-117">'T</span></span>

<span data-ttu-id="d76e2-118">Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="d76e2-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>