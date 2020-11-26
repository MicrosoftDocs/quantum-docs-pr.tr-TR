---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 45526c0202e417213aab3fe7819827588e794e23
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216396"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="576d7-102">UncurriedOpCA işlevi</span><span class="sxs-lookup"><span data-stu-id="576d7-102">UncurriedOpCA function</span></span>

<span data-ttu-id="576d7-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="576d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="576d7-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="576d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="576d7-105">İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="576d7-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="576d7-106">Değiştirici, `CA` işlemlerin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="576d7-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="576d7-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="576d7-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="576d7-108">curriedOp: 'T-> ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="576d7-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="576d7-109">İşlemleri döndüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="576d7-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="576d7-110">Çıkış: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="576d7-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="576d7-111">`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="576d7-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="576d7-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="576d7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="576d7-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="576d7-113">'T</span></span>

<span data-ttu-id="576d7-114">Bir curried işlevinin ilk bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="576d7-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="576d7-115">' U</span><span class="sxs-lookup"><span data-stu-id="576d7-115">'U</span></span>

<span data-ttu-id="576d7-116">Bir curried işlevinin ikinci bağımsız değişkeninin türü.</span><span class="sxs-lookup"><span data-stu-id="576d7-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="576d7-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="576d7-117">See Also</span></span>

- [<span data-ttu-id="576d7-118">Microsoft. hisse. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="576d7-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)