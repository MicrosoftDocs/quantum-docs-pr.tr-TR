---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: a26cc178f67fd99324355ac230d9e91081b6e238
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204938"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="905c5-102">TransformedOperation işlevi</span><span class="sxs-lookup"><span data-stu-id="905c5-102">TransformedOperation function</span></span>

<span data-ttu-id="905c5-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="905c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="905c5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="905c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="905c5-105">Bir işlev ve bir işlem verildiğinde, girişi verilen işlev tarafından dönüştürülen yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="905c5-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="905c5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="905c5-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="905c5-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="905c5-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="905c5-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="905c5-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="905c5-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="905c5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="905c5-110">Dönüştürülecek işlem.</span><span class="sxs-lookup"><span data-stu-id="905c5-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="905c5-111">Çıkış: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="905c5-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="905c5-112">Yeni bir işlem olan tbat `fn` , girişiyle birlikte çağrı yapar ve sonuç çıktısını öğesine geçirir `op` .</span><span class="sxs-lookup"><span data-stu-id="905c5-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="905c5-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="905c5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="905c5-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="905c5-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="905c5-115">' U</span><span class="sxs-lookup"><span data-stu-id="905c5-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="905c5-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="905c5-116">See Also</span></span>

- [<span data-ttu-id="905c5-117">Microsoft. hisse. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="905c5-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="905c5-118">Microsoft. hisse. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="905c5-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="905c5-119">Microsoft. hisse. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="905c5-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="905c5-120">Microsoft. hisse. Canon. Applywithınputtransformation</span><span class="sxs-lookup"><span data-stu-id="905c5-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="905c5-121">Microsoft. hisse. Canon. oluşturulan</span><span class="sxs-lookup"><span data-stu-id="905c5-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)