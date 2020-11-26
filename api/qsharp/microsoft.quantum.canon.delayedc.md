---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207028"
---
# <a name="delayedc-function"></a><span data-ttu-id="b10c5-102">DelayedC işlevi</span><span class="sxs-lookup"><span data-stu-id="b10c5-102">DelayedC function</span></span>

<span data-ttu-id="b10c5-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b10c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b10c5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b10c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b10c5-105">Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="b10c5-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="b10c5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b10c5-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="b10c5-107">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="b10c5-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="b10c5-108">Dönüş değeri uygulama sonucu olarak uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="b10c5-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="b10c5-109">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="b10c5-109">arg : 'T</span></span>

<span data-ttu-id="b10c5-110">İşlemin `op` uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="b10c5-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="b10c5-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit) => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL 'dir</span><span class="sxs-lookup"><span data-stu-id="b10c5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="b10c5-112">Giriş ile uygulanan yeni bir işlem `op``arg`</span><span class="sxs-lookup"><span data-stu-id="b10c5-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b10c5-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="b10c5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b10c5-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="b10c5-114">'T</span></span>

<span data-ttu-id="b10c5-115">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="b10c5-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="b10c5-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b10c5-116">See Also</span></span>

- [<span data-ttu-id="b10c5-117">Microsoft. hisse. Canon. Gecikmeli</span><span class="sxs-lookup"><span data-stu-id="b10c5-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="b10c5-118">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="b10c5-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)