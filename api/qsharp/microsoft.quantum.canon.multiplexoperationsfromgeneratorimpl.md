---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGeneratorImpl
title: Çoğullexoperationsfromgeneratorimpl işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGeneratorImpl
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 68c9fcf7ee7893dc3ef6600cc5d6c5be807f9eb4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852478"
---
# <a name="multiplexoperationsfromgeneratorimpl-operation"></a><span data-ttu-id="4f785-102">Çoğullexoperationsfromgeneratorimpl işlemi</span><span class="sxs-lookup"><span data-stu-id="4f785-102">MultiplexOperationsFromGeneratorImpl operation</span></span>

<span data-ttu-id="4f785-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4f785-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4f785-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f785-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f785-105">Uygulamasının uygulama adımı `MultiplexOperationsFromGenerator` .</span><span class="sxs-lookup"><span data-stu-id="4f785-105">Implementation step of `MultiplexOperationsFromGenerator`.</span></span>

```qsharp
operation MultiplexOperationsFromGeneratorImpl<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4f785-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4f785-106">Input</span></span>

### <a name="unitarygenerator--intintint---t--unit--is-adj--ctl"></a><span data-ttu-id="4f785-107">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 't => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL)</span><span class="sxs-lookup"><span data-stu-id="4f785-107">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="4f785-108">yardımcı: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4f785-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="4f785-109">Dizin: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4f785-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="4f785-110">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="4f785-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="4f785-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f785-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4f785-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4f785-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4f785-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4f785-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="4f785-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4f785-114">See Also</span></span>

- [<span data-ttu-id="4f785-115">Microsoft. hisse. Canon. MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="4f785-115">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)