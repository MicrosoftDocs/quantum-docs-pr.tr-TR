---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848597"
---
# <a name="fold-function"></a><span data-ttu-id="68c3e-102">Fold işlevi</span><span class="sxs-lookup"><span data-stu-id="68c3e-102">Fold function</span></span>

<span data-ttu-id="68c3e-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="68c3e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="68c3e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68c3e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68c3e-105">Bir işlevi bir `f` dizi aracılığıyla yineler `array` , döndürür `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="68c3e-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="68c3e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="68c3e-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="68c3e-107">klasör: (' durum, 'T)-> ' durumu</span><span class="sxs-lookup"><span data-stu-id="68c3e-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="68c3e-108">Dizi üzerinde katlanmak için bir işlev.</span><span class="sxs-lookup"><span data-stu-id="68c3e-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="68c3e-109">durum: ' durum</span><span class="sxs-lookup"><span data-stu-id="68c3e-109">state : 'State</span></span>

<span data-ttu-id="68c3e-110">Klasörün başlangıç durumu.</span><span class="sxs-lookup"><span data-stu-id="68c3e-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="68c3e-111">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="68c3e-111">array : 'T[]</span></span>

<span data-ttu-id="68c3e-112">Üzerine katlanır değer dizisi.</span><span class="sxs-lookup"><span data-stu-id="68c3e-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="68c3e-113">Çıkış: ' durum</span><span class="sxs-lookup"><span data-stu-id="68c3e-113">Output : 'State</span></span>

<span data-ttu-id="68c3e-114">Tüm öğelerinin üzerinde yinelendikten sonra klasör tarafından döndürülen son durum `array` .</span><span class="sxs-lookup"><span data-stu-id="68c3e-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="68c3e-115">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="68c3e-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="68c3e-116">' Durum</span><span class="sxs-lookup"><span data-stu-id="68c3e-116">'State</span></span>

<span data-ttu-id="68c3e-117">`folder`İşlevin üzerinde çalıştığı durumların türü, yani ilk bağımsız değişkeni olarak kabul eder ve döndürür.</span><span class="sxs-lookup"><span data-stu-id="68c3e-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="68c3e-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="68c3e-118">'T</span></span>

<span data-ttu-id="68c3e-119">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="68c3e-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="68c3e-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="68c3e-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```