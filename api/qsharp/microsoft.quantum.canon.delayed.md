---
uid: Microsoft.Quantum.Canon.Delayed
title: Gecikmeli işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 863c63d0c1a50339e9d5b9fbe4729932b2706f32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216464"
---
# <a name="delayed-function"></a><span data-ttu-id="0b7e0-102">Gecikmeli işlev</span><span class="sxs-lookup"><span data-stu-id="0b7e0-102">Delayed function</span></span>

<span data-ttu-id="0b7e0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0b7e0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0b7e0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b7e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b7e0-105">Verilen bağımsız değişkenle belirli bir işlem uygulayan bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="0b7e0-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="0b7e0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0b7e0-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="0b7e0-107">Op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="0b7e0-107">op : 'T => 'U</span></span> 

<span data-ttu-id="0b7e0-108">Uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="0b7e0-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="0b7e0-109">bağımsız değişken: 'T</span><span class="sxs-lookup"><span data-stu-id="0b7e0-109">arg : 'T</span></span>

<span data-ttu-id="0b7e0-110">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="0b7e0-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="0b7e0-111">Çıkış: [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="0b7e0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="0b7e0-112">Giriş ile uygulanan yeni bir işlem `op``arg`</span><span class="sxs-lookup"><span data-stu-id="0b7e0-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b7e0-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="0b7e0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b7e0-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="0b7e0-114">'T</span></span>

<span data-ttu-id="0b7e0-115">Gecikecek işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="0b7e0-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="0b7e0-116">' U</span><span class="sxs-lookup"><span data-stu-id="0b7e0-116">'U</span></span>

<span data-ttu-id="0b7e0-117">Gecikecek işlemin dönüş türü.</span><span class="sxs-lookup"><span data-stu-id="0b7e0-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b7e0-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0b7e0-118">See Also</span></span>

- [<span data-ttu-id="0b7e0-119">Microsoft. hisse. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="0b7e0-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="0b7e0-120">Microsoft. hisse. Canon. DelayedA</span><span class="sxs-lookup"><span data-stu-id="0b7e0-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="0b7e0-121">Microsoft. hisse. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="0b7e0-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="0b7e0-122">Microsoft. hisse. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="0b7e0-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)