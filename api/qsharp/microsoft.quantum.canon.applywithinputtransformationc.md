---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Applywithınputtransform Tionc işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: f166880d3ca8a7fc45635c0105aa5c83fe1b4f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728988"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="38929-102">Applywithınputtransform Tionc işlemi</span><span class="sxs-lookup"><span data-stu-id="38929-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="38929-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="38929-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="38929-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38929-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38929-105">Bazı girişleri kabul eden bir işlem, bu işlemle uyumlu bir çıkış döndüren bir işlev ve bu işleve bir giriş verildiğinde, girişi işlemin beklenen bir biçime dönüştürmek için işlevini kullanarak işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="38929-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="38929-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="38929-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="38929-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="38929-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="38929-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="38929-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="38929-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="38929-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="38929-110">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="38929-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="38929-111">Giriş: ' U</span><span class="sxs-lookup"><span data-stu-id="38929-111">input : 'U</span></span>

<span data-ttu-id="38929-112">İşleve bir giriş.</span><span class="sxs-lookup"><span data-stu-id="38929-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="38929-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38929-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="38929-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="38929-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="38929-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="38929-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="38929-116">' U</span><span class="sxs-lookup"><span data-stu-id="38929-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="38929-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="38929-117">See Also</span></span>

- [<span data-ttu-id="38929-118">Microsoft. hisse. Canon. Applywithınputtransformation</span><span class="sxs-lookup"><span data-stu-id="38929-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="38929-119">Microsoft. hisse. Canon. Applywithınputtransform Tiona</span><span class="sxs-lookup"><span data-stu-id="38929-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="38929-120">Microsoft. hisse. Canon. Applywithınputtransform Tionca</span><span class="sxs-lookup"><span data-stu-id="38929-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="38929-121">Microsoft. hisse. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="38929-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)