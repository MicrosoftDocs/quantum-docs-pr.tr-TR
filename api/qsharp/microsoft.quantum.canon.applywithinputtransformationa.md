---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Applywithınputtransform Tiona işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b72c131691e08b4bd32b7faf9265aad6c52b7fde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728993"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="1d2a1-102">Applywithınputtransform Tiona işlemi</span><span class="sxs-lookup"><span data-stu-id="1d2a1-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="1d2a1-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1d2a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1d2a1-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1d2a1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1d2a1-105">Bazı girişleri kabul eden bir işlem, bu işlemle uyumlu bir çıkış döndüren bir işlev ve bu işleve bir giriş verildiğinde, girişi işlemin beklenen bir biçime dönüştürmek için işlevini kullanarak işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="1d2a1-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="1d2a1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1d2a1-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="1d2a1-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="1d2a1-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="1d2a1-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="1d2a1-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="1d2a1-109">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="1d2a1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1d2a1-110">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="1d2a1-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="1d2a1-111">Giriş: ' U</span><span class="sxs-lookup"><span data-stu-id="1d2a1-111">input : 'U</span></span>

<span data-ttu-id="1d2a1-112">İşleve bir giriş.</span><span class="sxs-lookup"><span data-stu-id="1d2a1-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d2a1-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d2a1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1d2a1-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="1d2a1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1d2a1-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="1d2a1-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="1d2a1-116">' U</span><span class="sxs-lookup"><span data-stu-id="1d2a1-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="1d2a1-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1d2a1-117">See Also</span></span>

- [<span data-ttu-id="1d2a1-118">Microsoft. hisse. Canon. Applywithınputtransformation</span><span class="sxs-lookup"><span data-stu-id="1d2a1-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="1d2a1-119">Microsoft. hisse. Canon. Applywithınputtransform Tionc</span><span class="sxs-lookup"><span data-stu-id="1d2a1-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="1d2a1-120">Microsoft. hisse. Canon. Applywithınputtransform Tionca</span><span class="sxs-lookup"><span data-stu-id="1d2a1-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="1d2a1-121">Microsoft. hisse. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="1d2a1-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)