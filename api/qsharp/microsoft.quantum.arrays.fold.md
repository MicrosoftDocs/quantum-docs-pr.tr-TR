---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730242"
---
# <a name="fold-function"></a><span data-ttu-id="046a4-102">Fold işlevi</span><span class="sxs-lookup"><span data-stu-id="046a4-102">Fold function</span></span>

<span data-ttu-id="046a4-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="046a4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="046a4-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="046a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="046a4-105">Bir işlevi bir `f` dizi aracılığıyla yineler `array` , döndürür `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="046a4-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="046a4-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="046a4-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="046a4-107">klasör: (' durum, 'T)-> ' durumu</span><span class="sxs-lookup"><span data-stu-id="046a4-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="046a4-108">Dizi üzerinde katlanmak için bir işlev.</span><span class="sxs-lookup"><span data-stu-id="046a4-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="046a4-109">durum: ' durum</span><span class="sxs-lookup"><span data-stu-id="046a4-109">state : 'State</span></span>

<span data-ttu-id="046a4-110">Klasörün başlangıç durumu.</span><span class="sxs-lookup"><span data-stu-id="046a4-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="046a4-111">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="046a4-111">array : 'T[]</span></span>

<span data-ttu-id="046a4-112">Üzerine katlanır değer dizisi.</span><span class="sxs-lookup"><span data-stu-id="046a4-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="046a4-113">Çıkış: ' durum</span><span class="sxs-lookup"><span data-stu-id="046a4-113">Output : 'State</span></span>

<span data-ttu-id="046a4-114">Tüm öğelerinin üzerinde yinelendikten sonra klasör tarafından döndürülen son durum `array` .</span><span class="sxs-lookup"><span data-stu-id="046a4-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="046a4-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="046a4-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="046a4-116">' Durum</span><span class="sxs-lookup"><span data-stu-id="046a4-116">'State</span></span>

<span data-ttu-id="046a4-117">`folder`İşlevin üzerinde çalıştığı durumların türü, yani ilk bağımsız değişkeni olarak kabul eder ve döndürür.</span><span class="sxs-lookup"><span data-stu-id="046a4-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="046a4-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="046a4-118">'T</span></span>

<span data-ttu-id="046a4-119">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="046a4-119">The type of `array` elements.</span></span>