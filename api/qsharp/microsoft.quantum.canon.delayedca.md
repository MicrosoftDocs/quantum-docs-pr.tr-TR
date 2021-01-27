---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: c44e3448c471f2a20f995d4546ee54f3affb726e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840543"
---
# <a name="delayedca-function"></a><span data-ttu-id="482c1-102">DelayedCA işlevi</span><span class="sxs-lookup"><span data-stu-id="482c1-102">DelayedCA function</span></span>

<span data-ttu-id="482c1-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="482c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="482c1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="482c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="482c1-105">Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="482c1-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="482c1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="482c1-106">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="482c1-107">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="482c1-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="482c1-108">Dönüş değeri uygulama sonucu olarak uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="482c1-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="482c1-109">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="482c1-109">arg : 'T</span></span>

<span data-ttu-id="482c1-110">İşlemin `op` uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="482c1-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj--ctl"></a><span data-ttu-id="482c1-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="482c1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="482c1-112">Giriş ile uygulanan yeni bir işlem `op``arg`</span><span class="sxs-lookup"><span data-stu-id="482c1-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="482c1-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="482c1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="482c1-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="482c1-114">'T</span></span>

<span data-ttu-id="482c1-115">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="482c1-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="482c1-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="482c1-116">See Also</span></span>

- [<span data-ttu-id="482c1-117">Microsoft. hisse. Canon. Gecikmeli</span><span class="sxs-lookup"><span data-stu-id="482c1-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="482c1-118">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="482c1-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)