---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Trotter1ImplCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 250b80729530a5d3054e037d9dd653904a57f6d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728328"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="83cb0-102">Trotter1ImplCA işlemi</span><span class="sxs-lookup"><span data-stu-id="83cb0-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="83cb0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="83cb0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="83cb0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83cb0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83cb0-105">İlk sipariş rahatlığını – Suzuki tümleştirici uygulama.</span><span class="sxs-lookup"><span data-stu-id="83cb0-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="83cb0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="83cb0-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="83cb0-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83cb0-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83cb0-108">Zaman adımlarında kaldırılacak işlem sayısı.</span><span class="sxs-lookup"><span data-stu-id="83cb0-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="83cb0-109">Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="83cb0-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="83cb0-110">Bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü `Double` ) ve ayrıştırma için bir hisse kayıt (tür) kabul eden bir işlem `'T` .</span><span class="sxs-lookup"><span data-stu-id="83cb0-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="83cb0-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="83cb0-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="83cb0-112">Simülasyonun her adımının boyut çarpanı.</span><span class="sxs-lookup"><span data-stu-id="83cb0-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="83cb0-113">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="83cb0-113">target : 'T</span></span>

<span data-ttu-id="83cb0-114">İşlemlerin davranabileceği bir hisse kayıt.</span><span class="sxs-lookup"><span data-stu-id="83cb0-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="83cb0-115">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="83cb0-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="83cb0-116">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="83cb0-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="83cb0-117">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="83cb0-117">'T</span></span>

<span data-ttu-id="83cb0-118">Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="83cb0-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>