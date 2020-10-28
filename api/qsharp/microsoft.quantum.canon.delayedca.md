---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728723"
---
# <a name="delayedca-function"></a><span data-ttu-id="d80a6-102">DelayedCA işlevi</span><span class="sxs-lookup"><span data-stu-id="d80a6-102">DelayedCA function</span></span>

<span data-ttu-id="d80a6-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d80a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d80a6-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d80a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d80a6-105">Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="d80a6-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="d80a6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="d80a6-106">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="d80a6-107">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + sıfatı</span><span class="sxs-lookup"><span data-stu-id="d80a6-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d80a6-108">Dönüş değeri uygulama sonucu olarak uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="d80a6-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="d80a6-109">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="d80a6-109">arg : 'T</span></span>

<span data-ttu-id="d80a6-110">İşlemin `op` uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="d80a6-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl--adj"></a><span data-ttu-id="d80a6-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL + ayarlanabilir</span><span class="sxs-lookup"><span data-stu-id="d80a6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="d80a6-112">Giriş ile uygulanan yeni bir işlem `op``arg`</span><span class="sxs-lookup"><span data-stu-id="d80a6-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d80a6-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="d80a6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d80a6-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="d80a6-114">'T</span></span>

<span data-ttu-id="d80a6-115">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="d80a6-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="d80a6-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d80a6-116">See Also</span></span>

- [<span data-ttu-id="d80a6-117">Microsoft. hisse. Canon. Gecikmeli</span><span class="sxs-lookup"><span data-stu-id="d80a6-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="d80a6-118">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="d80a6-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)