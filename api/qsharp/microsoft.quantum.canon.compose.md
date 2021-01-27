---
uid: Microsoft.Quantum.Canon.Compose
title: Compose işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840901"
---
# <a name="compose-function"></a><span data-ttu-id="e1fa1-102">Compose işlevi</span><span class="sxs-lookup"><span data-stu-id="e1fa1-102">Compose function</span></span>

<span data-ttu-id="e1fa1-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e1fa1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e1fa1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1fa1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1fa1-105">İki işlevin birleşimini döndürür.</span><span class="sxs-lookup"><span data-stu-id="e1fa1-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="e1fa1-106">Description</span><span class="sxs-lookup"><span data-stu-id="e1fa1-106">Description</span></span>

<span data-ttu-id="e1fa1-107">$ Ve $g $ $f iki işlev verildiğinde, $f \circ g $ temsil eden yeni bir işlev döndürür.</span><span class="sxs-lookup"><span data-stu-id="e1fa1-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="e1fa1-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="e1fa1-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="e1fa1-109">Dış: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="e1fa1-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="e1fa1-110">Uygulanacak ikinci işlev.</span><span class="sxs-lookup"><span data-stu-id="e1fa1-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="e1fa1-111">iç: 'T-> ' U</span><span class="sxs-lookup"><span data-stu-id="e1fa1-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="e1fa1-112">Uygulanacak ilk işlev.</span><span class="sxs-lookup"><span data-stu-id="e1fa1-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="e1fa1-113">Çıkış: 'T-> ' V</span><span class="sxs-lookup"><span data-stu-id="e1fa1-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="e1fa1-114">$, $F (g (x)) = h (x) $ $x tüm girişler için $h $ gibi yeni bir işlev.</span><span class="sxs-lookup"><span data-stu-id="e1fa1-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e1fa1-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e1fa1-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1fa1-116">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e1fa1-116">'T</span></span>

<span data-ttu-id="e1fa1-117">Uygulanacak ilk işlevin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="e1fa1-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="e1fa1-118">' U</span><span class="sxs-lookup"><span data-stu-id="e1fa1-118">'U</span></span>

<span data-ttu-id="e1fa1-119">Uygulanacak ilk işlevin çıkış türü ve uygulanacak ikinci işlevin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="e1fa1-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="e1fa1-120">' V</span><span class="sxs-lookup"><span data-stu-id="e1fa1-120">'V</span></span>

<span data-ttu-id="e1fa1-121">Uygulanacak ikinci işlevin çıkış türü.</span><span class="sxs-lookup"><span data-stu-id="e1fa1-121">The output type of the second function to be applied.</span></span>