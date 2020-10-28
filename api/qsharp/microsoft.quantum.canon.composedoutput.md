---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728837"
---
# <a name="composedoutput-function"></a><span data-ttu-id="b812c-102">ComposedOutput işlevi</span><span class="sxs-lookup"><span data-stu-id="b812c-102">ComposedOutput function</span></span>

<span data-ttu-id="b812c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b812c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b812c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b812c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b812c-105">`inner`Belirli bir girdi için ve öğesinin kompozisyonunun çıkışını döndürür `outer` .</span><span class="sxs-lookup"><span data-stu-id="b812c-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="b812c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b812c-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="b812c-107">Dış: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="b812c-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="b812c-108">iç: 'T-> ' U</span><span class="sxs-lookup"><span data-stu-id="b812c-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="b812c-109">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="b812c-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="b812c-110">Çıkış: ' V</span><span class="sxs-lookup"><span data-stu-id="b812c-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b812c-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="b812c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b812c-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="b812c-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="b812c-113">' U</span><span class="sxs-lookup"><span data-stu-id="b812c-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="b812c-114">' V</span><span class="sxs-lookup"><span data-stu-id="b812c-114">'V</span></span>

