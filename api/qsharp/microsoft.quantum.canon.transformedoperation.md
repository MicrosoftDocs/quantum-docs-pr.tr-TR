---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728345"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="78a95-102">TransformedOperation işlevi</span><span class="sxs-lookup"><span data-stu-id="78a95-102">TransformedOperation function</span></span>

<span data-ttu-id="78a95-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="78a95-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="78a95-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78a95-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78a95-105">Bir işlev ve bir işlem verildiğinde, girişi verilen işlev tarafından dönüştürülen yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="78a95-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="78a95-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="78a95-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="78a95-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="78a95-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="78a95-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="78a95-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="78a95-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78a95-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="78a95-110">Dönüştürülecek işlem.</span><span class="sxs-lookup"><span data-stu-id="78a95-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="78a95-111">Çıkış: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78a95-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="78a95-112">Yeni bir işlem olan tbat `fn` , girişiyle birlikte çağrı yapar ve sonuç çıktısını öğesine geçirir `op` .</span><span class="sxs-lookup"><span data-stu-id="78a95-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="78a95-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="78a95-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="78a95-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="78a95-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="78a95-115">' U</span><span class="sxs-lookup"><span data-stu-id="78a95-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="78a95-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="78a95-116">See Also</span></span>

- [<span data-ttu-id="78a95-117">Microsoft. hisse. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="78a95-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="78a95-118">Microsoft. hisse. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="78a95-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="78a95-119">Microsoft. hisse. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="78a95-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="78a95-120">Microsoft. hisse. Canon. Applywithınputtransformation</span><span class="sxs-lookup"><span data-stu-id="78a95-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="78a95-121">Microsoft. hisse. Canon. oluşturulan</span><span class="sxs-lookup"><span data-stu-id="78a95-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)