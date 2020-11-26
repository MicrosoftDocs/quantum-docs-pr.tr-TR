---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207471"
---
# <a name="composedoutput-function"></a><span data-ttu-id="cb0f9-102">ComposedOutput işlevi</span><span class="sxs-lookup"><span data-stu-id="cb0f9-102">ComposedOutput function</span></span>

<span data-ttu-id="cb0f9-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cb0f9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cb0f9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb0f9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cb0f9-105">`inner`Belirli bir girdi için ve öğesinin kompozisyonunun çıkışını döndürür `outer` .</span><span class="sxs-lookup"><span data-stu-id="cb0f9-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="cb0f9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cb0f9-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="cb0f9-107">Dış: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="cb0f9-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="cb0f9-108">iç: 'T-> ' U</span><span class="sxs-lookup"><span data-stu-id="cb0f9-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="cb0f9-109">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="cb0f9-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="cb0f9-110">Çıkış: ' V</span><span class="sxs-lookup"><span data-stu-id="cb0f9-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cb0f9-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="cb0f9-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cb0f9-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="cb0f9-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="cb0f9-113">' U</span><span class="sxs-lookup"><span data-stu-id="cb0f9-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="cb0f9-114">' V</span><span class="sxs-lookup"><span data-stu-id="cb0f9-114">'V</span></span>

