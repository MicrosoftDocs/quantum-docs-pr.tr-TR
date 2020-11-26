---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: Applywithınputtransform Tiona işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 8d65af33a0bc8ce3c08da54b34e68b4e22b710ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207896"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="9ca0a-102">Applywithınputtransform Tiona işlemi</span><span class="sxs-lookup"><span data-stu-id="9ca0a-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="9ca0a-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9ca0a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9ca0a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ca0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ca0a-105">Bazı girişleri kabul eden bir işlem, bu işlemle uyumlu bir çıkış döndüren bir işlev ve bu işleve bir giriş verildiğinde, girişi işlemin beklenen bir biçime dönüştürmek için işlevini kullanarak işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="9ca0a-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="9ca0a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9ca0a-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="9ca0a-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="9ca0a-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="9ca0a-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="9ca0a-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="9ca0a-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="9ca0a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9ca0a-110">Uygulanacak işlem.</span><span class="sxs-lookup"><span data-stu-id="9ca0a-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="9ca0a-111">Giriş: ' U</span><span class="sxs-lookup"><span data-stu-id="9ca0a-111">input : 'U</span></span>

<span data-ttu-id="9ca0a-112">İşleve bir giriş.</span><span class="sxs-lookup"><span data-stu-id="9ca0a-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ca0a-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ca0a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9ca0a-114">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9ca0a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9ca0a-115">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9ca0a-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="9ca0a-116">' U</span><span class="sxs-lookup"><span data-stu-id="9ca0a-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="9ca0a-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9ca0a-117">See Also</span></span>

- [<span data-ttu-id="9ca0a-118">Microsoft. hisse. Canon. Applywithınputtransformation</span><span class="sxs-lookup"><span data-stu-id="9ca0a-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="9ca0a-119">Microsoft. hisse. Canon. Applywithınputtransform Tionc</span><span class="sxs-lookup"><span data-stu-id="9ca0a-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="9ca0a-120">Microsoft. hisse. Canon. Applywithınputtransform Tionca</span><span class="sxs-lookup"><span data-stu-id="9ca0a-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="9ca0a-121">Microsoft. hisse. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="9ca0a-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)