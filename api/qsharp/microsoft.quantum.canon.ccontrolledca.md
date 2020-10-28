---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728873"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="f7f2b-102">CControlledCA işlevi</span><span class="sxs-lookup"><span data-stu-id="f7f2b-102">CControlledCA function</span></span>

<span data-ttu-id="f7f2b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7f2b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7f2b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7f2b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7f2b-105">Bir işlem işlemi verildiğinde, bir klasik denetim biti doğru ise op 'yi uygulayan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="f7f2b-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="f7f2b-106">Yoksa `false` , hiçbir şey olmaz.</span><span class="sxs-lookup"><span data-stu-id="f7f2b-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="f7f2b-107">Değiştirici, `CA` işlemin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="f7f2b-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="f7f2b-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="f7f2b-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="f7f2b-109">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) CTL + sıfatı</span><span class="sxs-lookup"><span data-stu-id="f7f2b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="f7f2b-110">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="f7f2b-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="f7f2b-111">Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) CTL + ayarlama</span><span class="sxs-lookup"><span data-stu-id="f7f2b-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="f7f2b-112">Klasik denetim biti doğru ise op olan yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="f7f2b-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f7f2b-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="f7f2b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7f2b-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="f7f2b-114">'T</span></span>

<span data-ttu-id="f7f2b-115">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="f7f2b-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7f2b-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f7f2b-116">See Also</span></span>

- [<span data-ttu-id="f7f2b-117">Microsoft. hisse. Canon. Cdenetimli</span><span class="sxs-lookup"><span data-stu-id="f7f2b-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)