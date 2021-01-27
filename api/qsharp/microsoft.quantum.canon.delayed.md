---
uid: Microsoft.Quantum.Canon.Delayed
title: Gecikmeli işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840579"
---
# <a name="delayed-function"></a><span data-ttu-id="9784c-102">Gecikmeli işlev</span><span class="sxs-lookup"><span data-stu-id="9784c-102">Delayed function</span></span>

<span data-ttu-id="9784c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9784c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9784c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9784c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9784c-105">Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="9784c-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="9784c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9784c-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="9784c-107">Op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="9784c-107">op : 'T => 'U</span></span> 

<span data-ttu-id="9784c-108">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="9784c-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="9784c-109">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="9784c-109">arg : 'T</span></span>

<span data-ttu-id="9784c-110">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="9784c-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="9784c-111">Çıkış: [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="9784c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="9784c-112">Giriş ile uygulanan yeni bir işlem `op``arg`</span><span class="sxs-lookup"><span data-stu-id="9784c-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9784c-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9784c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9784c-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="9784c-114">'T</span></span>

<span data-ttu-id="9784c-115">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="9784c-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="9784c-116">' U</span><span class="sxs-lookup"><span data-stu-id="9784c-116">'U</span></span>

<span data-ttu-id="9784c-117">Gecikecek işlemin dönüş türü.</span><span class="sxs-lookup"><span data-stu-id="9784c-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="9784c-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9784c-118">See Also</span></span>

- [<span data-ttu-id="9784c-119">Microsoft. hisse. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="9784c-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="9784c-120">Microsoft. hisse. Canon. DelayedA</span><span class="sxs-lookup"><span data-stu-id="9784c-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="9784c-121">Microsoft. hisse. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="9784c-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="9784c-122">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="9784c-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)