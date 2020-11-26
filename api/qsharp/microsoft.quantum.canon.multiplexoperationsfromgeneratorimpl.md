---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGeneratorImpl
title: Çoğullexoperationsfromgeneratorimpl işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGeneratorImpl
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 98ba9cd24f04b8417cb176ee1630402483bc3b52
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206060"
---
# <a name="multiplexoperationsfromgeneratorimpl-operation"></a><span data-ttu-id="7d915-102">Çoğullexoperationsfromgeneratorimpl işlemi</span><span class="sxs-lookup"><span data-stu-id="7d915-102">MultiplexOperationsFromGeneratorImpl operation</span></span>

<span data-ttu-id="7d915-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7d915-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7d915-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d915-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d915-105">Uygulamasının uygulama adımı `MultiplexOperationsFromGenerator` .</span><span class="sxs-lookup"><span data-stu-id="7d915-105">Implementation step of `MultiplexOperationsFromGenerator`.</span></span>

```qsharp
operation MultiplexOperationsFromGeneratorImpl<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7d915-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7d915-106">Input</span></span>

### <a name="unitarygenerator--intintint---t--unit--is-adj--ctl"></a><span data-ttu-id="7d915-107">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 't => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL)</span><span class="sxs-lookup"><span data-stu-id="7d915-107">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="7d915-108">yardımcı: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7d915-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="7d915-109">Dizin: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7d915-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="7d915-110">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="7d915-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="7d915-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d915-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7d915-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="7d915-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d915-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="7d915-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="7d915-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7d915-114">See Also</span></span>

- [<span data-ttu-id="7d915-115">Microsoft. hisse. Canon. MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="7d915-115">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)