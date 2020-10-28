---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728718"
---
# <a name="delayedc-function"></a><span data-ttu-id="c5700-102">DelayedC işlevi</span><span class="sxs-lookup"><span data-stu-id="c5700-102">DelayedC function</span></span>

<span data-ttu-id="c5700-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c5700-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c5700-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5700-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5700-105">Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="c5700-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="c5700-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c5700-106">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="c5700-107">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="c5700-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c5700-108">Dönüş değeri uygulama sonucu olarak uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="c5700-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="c5700-109">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="c5700-109">arg : 'T</span></span>

<span data-ttu-id="c5700-110">İşlemin `op` uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="c5700-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl"></a><span data-ttu-id="c5700-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="c5700-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c5700-112">Giriş ile uygulanan yeni bir işlem `op``arg`</span><span class="sxs-lookup"><span data-stu-id="c5700-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c5700-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c5700-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5700-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c5700-114">'T</span></span>

<span data-ttu-id="c5700-115">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="c5700-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5700-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c5700-116">See Also</span></span>

- [<span data-ttu-id="c5700-117">Microsoft. hisse. Canon. Gecikmeli</span><span class="sxs-lookup"><span data-stu-id="c5700-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="c5700-118">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="c5700-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)