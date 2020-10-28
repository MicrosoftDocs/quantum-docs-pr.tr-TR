---
uid: Microsoft.Quantum.Canon.Compose
title: Compose işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728838"
---
# <a name="compose-function"></a><span data-ttu-id="df7e0-102">Compose işlevi</span><span class="sxs-lookup"><span data-stu-id="df7e0-102">Compose function</span></span>

<span data-ttu-id="df7e0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="df7e0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="df7e0-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df7e0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df7e0-105">İki işlevin birleşimini döndürür.</span><span class="sxs-lookup"><span data-stu-id="df7e0-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="df7e0-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="df7e0-106">Description</span></span>

<span data-ttu-id="df7e0-107">$ Ve $g $ $f iki işlev verildiğinde, $f \circ g $ temsil eden yeni bir işlev döndürür.</span><span class="sxs-lookup"><span data-stu-id="df7e0-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="df7e0-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="df7e0-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="df7e0-109">Dış: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="df7e0-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="df7e0-110">Uygulanacak ikinci işlev.</span><span class="sxs-lookup"><span data-stu-id="df7e0-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="df7e0-111">iç: 'T-> ' U</span><span class="sxs-lookup"><span data-stu-id="df7e0-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="df7e0-112">Uygulanacak ilk işlev.</span><span class="sxs-lookup"><span data-stu-id="df7e0-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="df7e0-113">Çıkış: 'T-> ' V</span><span class="sxs-lookup"><span data-stu-id="df7e0-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="df7e0-114">$, $F (g (x)) = h (x) $ $x tüm girişler için $h $ gibi yeni bir işlev.</span><span class="sxs-lookup"><span data-stu-id="df7e0-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="df7e0-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="df7e0-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="df7e0-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="df7e0-116">'T</span></span>

<span data-ttu-id="df7e0-117">Uygulanacak ilk işlevin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="df7e0-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="df7e0-118">' U</span><span class="sxs-lookup"><span data-stu-id="df7e0-118">'U</span></span>

<span data-ttu-id="df7e0-119">Uygulanacak ilk işlevin çıkış türü ve uygulanacak ikinci işlevin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="df7e0-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="df7e0-120">' V</span><span class="sxs-lookup"><span data-stu-id="df7e0-120">'V</span></span>

<span data-ttu-id="df7e0-121">Uygulanacak ikinci işlevin çıkış türü.</span><span class="sxs-lookup"><span data-stu-id="df7e0-121">The output type of the second function to be applied.</span></span>