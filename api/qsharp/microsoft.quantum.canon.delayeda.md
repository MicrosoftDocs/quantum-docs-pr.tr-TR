---
uid: Microsoft.Quantum.Canon.DelayedA
title: DelayedA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728735"
---
# <a name="delayeda-function"></a><span data-ttu-id="88791-102">DelayedA işlevi</span><span class="sxs-lookup"><span data-stu-id="88791-102">DelayedA function</span></span>

<span data-ttu-id="88791-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="88791-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="88791-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="88791-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="88791-105">Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="88791-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="88791-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="88791-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="88791-107">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="88791-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="88791-108">Dönüş değeri uygulama sonucu olarak uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="88791-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="88791-109">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="88791-109">arg : 'T</span></span>

<span data-ttu-id="88791-110">İşlemin `op` uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="88791-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="88791-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlaması</span><span class="sxs-lookup"><span data-stu-id="88791-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="88791-112">Giriş ile uygulanan yeni bir işlem `op``arg`</span><span class="sxs-lookup"><span data-stu-id="88791-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="88791-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="88791-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="88791-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="88791-114">'T</span></span>

<span data-ttu-id="88791-115">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="88791-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="88791-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="88791-116">See Also</span></span>

- [<span data-ttu-id="88791-117">Microsoft. hisse. Canon. Gecikmeli</span><span class="sxs-lookup"><span data-stu-id="88791-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="88791-118">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="88791-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)