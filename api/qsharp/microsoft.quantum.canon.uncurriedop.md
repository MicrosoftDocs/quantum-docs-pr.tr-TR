---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728303"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="c4e5f-102">UncurriedOp işlevi</span><span class="sxs-lookup"><span data-stu-id="c4e5f-102">UncurriedOp function</span></span>

<span data-ttu-id="c4e5f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4e5f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4e5f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4e5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4e5f-105">İşlemleri döndüren bir işlev verildiğinde, her iki girişi de tanımlama grubu olarak alan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="c4e5f-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="c4e5f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c4e5f-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="c4e5f-107">curriedOp: 'T-> ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4e5f-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c4e5f-108">İşlemleri döndüren bir işlev.</span><span class="sxs-lookup"><span data-stu-id="c4e5f-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="c4e5f-109">Çıkış: ('T, ' U) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4e5f-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c4e5f-110">`op`İle eşdeğer olan yeni bir işlem `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="c4e5f-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4e5f-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="c4e5f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4e5f-112">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="c4e5f-112">'T</span></span>

<span data-ttu-id="c4e5f-113">Bir curried işlemine ilk girişin türü.</span><span class="sxs-lookup"><span data-stu-id="c4e5f-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="c4e5f-114">' U</span><span class="sxs-lookup"><span data-stu-id="c4e5f-114">'U</span></span>

<span data-ttu-id="c4e5f-115">Bir curried işlemine ikinci girişin türü.</span><span class="sxs-lookup"><span data-stu-id="c4e5f-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4e5f-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c4e5f-116">See Also</span></span>

- [<span data-ttu-id="c4e5f-117">Microsoft. hisse. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="c4e5f-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="c4e5f-118">Microsoft. hisse. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="c4e5f-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="c4e5f-119">Microsoft. hisse. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="c4e5f-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)