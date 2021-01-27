---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852050"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="6bc45-102">TransformedOperation işlevi</span><span class="sxs-lookup"><span data-stu-id="6bc45-102">TransformedOperation function</span></span>

<span data-ttu-id="6bc45-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6bc45-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6bc45-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bc45-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bc45-105">Bir işlev ve bir işlem verildiğinde, girişi verilen işlev tarafından dönüştürülen yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="6bc45-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="6bc45-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6bc45-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="6bc45-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="6bc45-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="6bc45-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="6bc45-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="6bc45-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bc45-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6bc45-110">Dönüştürülecek işlem.</span><span class="sxs-lookup"><span data-stu-id="6bc45-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="6bc45-111">Çıkış: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bc45-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6bc45-112">Yeni bir işlem olan tbat `fn` , girişiyle birlikte çağrı yapar ve sonuç çıktısını öğesine geçirir `op` .</span><span class="sxs-lookup"><span data-stu-id="6bc45-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6bc45-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6bc45-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6bc45-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6bc45-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="6bc45-115">' U</span><span class="sxs-lookup"><span data-stu-id="6bc45-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="6bc45-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="6bc45-116">Example</span></span>

<span data-ttu-id="6bc45-117">Aşağıdaki çağrı, @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" giriş için tasarlanan bir işlemi @"Microsoft.Quantum.Arithmetic.BigEndian" , türü girdileri kabul eden bir işleme dönüştürmek için kullanır @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="6bc45-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="6bc45-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6bc45-118">See Also</span></span>

- [<span data-ttu-id="6bc45-119">Microsoft. hisse. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="6bc45-119">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="6bc45-120">Microsoft. hisse. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="6bc45-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="6bc45-121">Microsoft. hisse. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="6bc45-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="6bc45-122">Microsoft. hisse. Canon. Applywithınputtransformation</span><span class="sxs-lookup"><span data-stu-id="6bc45-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="6bc45-123">Microsoft. hisse. Canon. oluşturulan</span><span class="sxs-lookup"><span data-stu-id="6bc45-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)