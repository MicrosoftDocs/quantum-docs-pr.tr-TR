---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: Applywithınputtransformation işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728999"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="ab116-102">Applywithınputtransformation işlemi</span><span class="sxs-lookup"><span data-stu-id="ab116-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="ab116-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ab116-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ab116-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ab116-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ab116-105">Bazı girişleri kabul eden bir işlem, bu işlemle uyumlu bir çıkış döndüren bir işlev ve bu işleve bir giriş verildiğinde, girişi işlemin beklenen bir biçime dönüştürmek için işlevini kullanarak işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="ab116-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="ab116-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ab116-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="ab116-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="ab116-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="ab116-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="ab116-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="ab116-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab116-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ab116-110">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="ab116-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="ab116-111">Giriş: ' U</span><span class="sxs-lookup"><span data-stu-id="ab116-111">input : 'U</span></span>

<span data-ttu-id="ab116-112">İşleve bir giriş.</span><span class="sxs-lookup"><span data-stu-id="ab116-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ab116-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ab116-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ab116-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="ab116-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ab116-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="ab116-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="ab116-116">' U</span><span class="sxs-lookup"><span data-stu-id="ab116-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="ab116-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ab116-117">See Also</span></span>

- [<span data-ttu-id="ab116-118">Microsoft. hisse. Canon. Applywithınputtransform Tiona</span><span class="sxs-lookup"><span data-stu-id="ab116-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="ab116-119">Microsoft. hisse. Canon. Applywithınputtransform Tionc</span><span class="sxs-lookup"><span data-stu-id="ab116-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="ab116-120">Microsoft. hisse. Canon. Applywithınputtransform Tionca</span><span class="sxs-lookup"><span data-stu-id="ab116-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="ab116-121">Microsoft. hisse. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="ab116-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)