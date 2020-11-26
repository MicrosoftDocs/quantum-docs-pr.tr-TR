---
uid: Microsoft.Quantum.Canon.Compose
title: Compose işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216770"
---
# <a name="compose-function"></a><span data-ttu-id="bc761-102">Compose işlevi</span><span class="sxs-lookup"><span data-stu-id="bc761-102">Compose function</span></span>

<span data-ttu-id="bc761-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bc761-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bc761-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bc761-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bc761-105">İki işlevin birleşimini döndürür.</span><span class="sxs-lookup"><span data-stu-id="bc761-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="bc761-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="bc761-106">Description</span></span>

<span data-ttu-id="bc761-107">$ Ve $g $ $f iki işlev verildiğinde, $f \circ g $ temsil eden yeni bir işlev döndürür.</span><span class="sxs-lookup"><span data-stu-id="bc761-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="bc761-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="bc761-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="bc761-109">Dış: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="bc761-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="bc761-110">Uygulanacak ikinci işlev.</span><span class="sxs-lookup"><span data-stu-id="bc761-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="bc761-111">iç: 'T-> ' U</span><span class="sxs-lookup"><span data-stu-id="bc761-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="bc761-112">Uygulanacak ilk işlev.</span><span class="sxs-lookup"><span data-stu-id="bc761-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="bc761-113">Çıkış: 'T-> ' V</span><span class="sxs-lookup"><span data-stu-id="bc761-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="bc761-114">$, $F (g (x)) = h (x) $ $x tüm girişler için $h $ gibi yeni bir işlev.</span><span class="sxs-lookup"><span data-stu-id="bc761-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bc761-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="bc761-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc761-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="bc761-116">'T</span></span>

<span data-ttu-id="bc761-117">Uygulanacak ilk işlevin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="bc761-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="bc761-118">' U</span><span class="sxs-lookup"><span data-stu-id="bc761-118">'U</span></span>

<span data-ttu-id="bc761-119">Uygulanacak ilk işlevin çıkış türü ve uygulanacak ikinci işlevin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="bc761-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="bc761-120">' V</span><span class="sxs-lookup"><span data-stu-id="bc761-120">'V</span></span>

<span data-ttu-id="bc761-121">Uygulanacak ikinci işlevin çıkış türü.</span><span class="sxs-lookup"><span data-stu-id="bc761-121">The output type of the second function to be applied.</span></span>