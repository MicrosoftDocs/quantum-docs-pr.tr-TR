---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728333"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="27207-102">Trotter2ImplCA işlemi</span><span class="sxs-lookup"><span data-stu-id="27207-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="27207-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27207-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27207-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27207-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27207-105">İkinci sipariş rahatlığını – Suzuki tümleştirici uygulama.</span><span class="sxs-lookup"><span data-stu-id="27207-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="27207-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="27207-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="27207-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27207-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27207-108">Zaman adımlarında kaldırılacak işlem sayısı.</span><span class="sxs-lookup"><span data-stu-id="27207-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="27207-109">Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="27207-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="27207-110">Bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü `Double` ) ve ayrıştırma için bir hisse kayıt (tür) kabul eden bir işlem `'T` .</span><span class="sxs-lookup"><span data-stu-id="27207-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="27207-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27207-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="27207-112">Simülasyonun her adımının boyut çarpanı.</span><span class="sxs-lookup"><span data-stu-id="27207-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="27207-113">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="27207-113">target : 'T</span></span>

<span data-ttu-id="27207-114">İşlemlerin davranabileceği bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="27207-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27207-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27207-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="27207-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="27207-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="27207-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="27207-117">'T</span></span>

<span data-ttu-id="27207-118">Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="27207-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>