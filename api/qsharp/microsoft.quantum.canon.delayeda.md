---
uid: Microsoft.Quantum.Canon.DelayedA
title: DelayedA işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 33ff4dab36a6c6e17b9496a623f70b814c9f2fed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207080"
---
# <a name="delayeda-function"></a><span data-ttu-id="a1189-102">DelayedA işlevi</span><span class="sxs-lookup"><span data-stu-id="a1189-102">DelayedA function</span></span>

<span data-ttu-id="a1189-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a1189-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a1189-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1189-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1189-105">Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="a1189-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="a1189-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a1189-106">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="a1189-107">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="a1189-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a1189-108">Dönüş değeri uygulama sonucu olarak uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="a1189-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="a1189-109">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="a1189-109">arg : 'T</span></span>

<span data-ttu-id="a1189-110">İşlemin `op` uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="a1189-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj"></a><span data-ttu-id="a1189-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit) => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="a1189-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="a1189-112">Giriş ile uygulanan yeni bir işlem `op``arg`</span><span class="sxs-lookup"><span data-stu-id="a1189-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a1189-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="a1189-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a1189-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="a1189-114">'T</span></span>

<span data-ttu-id="a1189-115">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="a1189-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1189-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a1189-116">See Also</span></span>

- [<span data-ttu-id="a1189-117">Microsoft. hisse. Canon. Gecikmeli</span><span class="sxs-lookup"><span data-stu-id="a1189-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="a1189-118">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="a1189-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)