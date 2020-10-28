---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: Biriki katlanmış işlev
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730367"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="723dd-102">Biriki katlanmış işlev</span><span class="sxs-lookup"><span data-stu-id="723dd-102">CumulativeFolded function</span></span>

<span data-ttu-id="723dd-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="723dd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="723dd-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="723dd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="723dd-105">Eşlenmiş ve katlama işlevini tek bir işlevle birleştirir</span><span class="sxs-lookup"><span data-stu-id="723dd-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="723dd-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="723dd-106">Description</span></span>

<span data-ttu-id="723dd-107">Bu işlev, `fn` bir başlangıç durumundan başlayarak işlevi dizi üzerinden yineler `state` ve ilk durumu dahil etmez tüm ara değerlerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="723dd-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="723dd-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="723dd-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="723dd-109">FN: (' durum, 'T)-> ' durumu</span><span class="sxs-lookup"><span data-stu-id="723dd-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="723dd-110">Dizi üzerinde katlanmak için bir işlev</span><span class="sxs-lookup"><span data-stu-id="723dd-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="723dd-111">durum: ' durum</span><span class="sxs-lookup"><span data-stu-id="723dd-111">state : 'State</span></span>

<span data-ttu-id="723dd-112">Katlanın ilk durumu</span><span class="sxs-lookup"><span data-stu-id="723dd-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="723dd-113">dizi: 'T []</span><span class="sxs-lookup"><span data-stu-id="723dd-113">array : 'T[]</span></span>

<span data-ttu-id="723dd-114">Katlaneklenecek değer dizisi</span><span class="sxs-lookup"><span data-stu-id="723dd-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="723dd-115">Çıkış: ' State []</span><span class="sxs-lookup"><span data-stu-id="723dd-115">Output : 'State[]</span></span>

<span data-ttu-id="723dd-116">Son durum da dahil olmak üzere tüm ara durumlar, ilk durumu değil.</span><span class="sxs-lookup"><span data-stu-id="723dd-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="723dd-117">Çıktı dizisinin uzunluğu, ile aynı uzunluktadır `array` .</span><span class="sxs-lookup"><span data-stu-id="723dd-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="723dd-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="723dd-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="723dd-119">' Durum</span><span class="sxs-lookup"><span data-stu-id="723dd-119">'State</span></span>

<span data-ttu-id="723dd-120">İşlevin üzerinde çalıştığı durumların türü, `fn` Yani, ilk giriş ve dönüş olarak kabul eder.</span><span class="sxs-lookup"><span data-stu-id="723dd-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="723dd-121">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="723dd-121">'T</span></span>

<span data-ttu-id="723dd-122">`array`Öğelerin türü.</span><span class="sxs-lookup"><span data-stu-id="723dd-122">The type of `array` elements.</span></span>