---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: feb5da771ee6cb6a750fa76f9ffd8f5a3e0b5734
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840063"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="feac6-102">UncurriedOpA işlevi</span><span class="sxs-lookup"><span data-stu-id="feac6-102">UncurriedOpA function</span></span>

<span data-ttu-id="feac6-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="feac6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="feac6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="feac6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="feac6-105">İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="feac6-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="feac6-106">Değiştirici, `A` işlemlerin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="feac6-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="feac6-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="feac6-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="feac6-108">curriedOp: 'T-> ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="feac6-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="feac6-109">İşlemleri döndüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="feac6-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="feac6-110">Çıkış: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="feac6-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="feac6-111">`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="feac6-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="feac6-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="feac6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="feac6-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="feac6-113">'T</span></span>

<span data-ttu-id="feac6-114">Bir curried işlevinin ilk bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="feac6-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="feac6-115">' U</span><span class="sxs-lookup"><span data-stu-id="feac6-115">'U</span></span>

<span data-ttu-id="feac6-116">Bir curried işlevinin ikinci bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="feac6-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="feac6-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="feac6-117">See Also</span></span>

- [<span data-ttu-id="feac6-118">Microsoft. hisse. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="feac6-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)