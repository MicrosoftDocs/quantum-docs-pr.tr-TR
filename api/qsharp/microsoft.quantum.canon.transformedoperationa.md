---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: eceba260e601b73bdfa2de6ea6ab146820b5c59a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204887"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="463ec-102">TransformedOperationA işlevi</span><span class="sxs-lookup"><span data-stu-id="463ec-102">TransformedOperationA function</span></span>

<span data-ttu-id="463ec-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="463ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="463ec-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="463ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="463ec-105">Bir işlev ve bir işlem verildiğinde, girişi verilen işlev tarafından dönüştürülen yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="463ec-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="463ec-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="463ec-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="463ec-107">FN: ' U-> 'T</span><span class="sxs-lookup"><span data-stu-id="463ec-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="463ec-108">Verilen girişi işlem tarafından beklenen bir biçimde dönüştüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="463ec-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="463ec-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="463ec-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="463ec-110">Dönüştürülecek işlem.</span><span class="sxs-lookup"><span data-stu-id="463ec-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj"></a><span data-ttu-id="463ec-111">Çıkış: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="463ec-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="463ec-112">Yeni bir işlem olan tbat `fn` , girişiyle birlikte çağrı yapar ve sonuç çıktısını öğesine geçirir `op` .</span><span class="sxs-lookup"><span data-stu-id="463ec-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="463ec-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="463ec-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="463ec-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="463ec-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="463ec-115">' U</span><span class="sxs-lookup"><span data-stu-id="463ec-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="463ec-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="463ec-116">See Also</span></span>

- [<span data-ttu-id="463ec-117">Microsoft. hisse. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="463ec-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="463ec-118">Microsoft. hisse. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="463ec-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="463ec-119">Microsoft. hisse. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="463ec-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="463ec-120">Microsoft. hisse. Canon. Applywithınputtransformation</span><span class="sxs-lookup"><span data-stu-id="463ec-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="463ec-121">Microsoft. hisse. Canon. oluşturulan</span><span class="sxs-lookup"><span data-stu-id="463ec-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)