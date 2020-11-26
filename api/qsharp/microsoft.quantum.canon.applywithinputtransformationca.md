---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: Applywithınputtransform Tionca işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c81620555bff9449d6a3235dc7cfa56ca5206f04
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207794"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="457a4-102">Applywithınputtransform Tionca işlemi</span><span class="sxs-lookup"><span data-stu-id="457a4-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="457a4-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="457a4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="457a4-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="457a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="457a4-105">Bazı girişleri kabul eden bir işlem, bu işlemle uyumlu bir çıkış döndüren bir işlev ve bu işleve bir giriş verildiğinde, girişi işlemin beklenen bir biçime dönüştürmek için işlevini kullanarak işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="457a4-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="457a4-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="457a4-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="457a4-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="457a4-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="457a4-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="457a4-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="457a4-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="457a4-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="457a4-110">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="457a4-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="457a4-111">Giriş: ' U</span><span class="sxs-lookup"><span data-stu-id="457a4-111">input : 'U</span></span>

<span data-ttu-id="457a4-112">İşleve bir giriş.</span><span class="sxs-lookup"><span data-stu-id="457a4-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="457a4-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="457a4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="457a4-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="457a4-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="457a4-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="457a4-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="457a4-116">' U</span><span class="sxs-lookup"><span data-stu-id="457a4-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="457a4-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="457a4-117">See Also</span></span>

- [<span data-ttu-id="457a4-118">Microsoft. hisse. Canon. Applywithınputtransformation</span><span class="sxs-lookup"><span data-stu-id="457a4-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="457a4-119">Microsoft. hisse. Canon. Applywithınputtransform Tiona</span><span class="sxs-lookup"><span data-stu-id="457a4-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="457a4-120">Microsoft. hisse. Canon. Applywithınputtransform Tionc</span><span class="sxs-lookup"><span data-stu-id="457a4-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="457a4-121">Microsoft. hisse. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="457a4-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)