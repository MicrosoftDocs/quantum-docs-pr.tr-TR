---
uid: Microsoft.Quantum.Canon.CControlledC
title: CControlledC işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledC
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: a10c8f0f835fe7cbb8f2d89d521a548169613c0a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840973"
---
# <a name="ccontrolledc-function"></a><span data-ttu-id="da36b-102">CControlledC işlevi</span><span class="sxs-lookup"><span data-stu-id="da36b-102">CControlledC function</span></span>

<span data-ttu-id="da36b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="da36b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="da36b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da36b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da36b-105">Bir işlem işlemi verildiğinde, bir klasik denetim biti doğru ise op 'yi uygulayan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="da36b-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="da36b-106">Yoksa `false` , hiçbir şey olmaz.</span><span class="sxs-lookup"><span data-stu-id="da36b-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="da36b-107">Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="da36b-107">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
function CControlledC<'T> (op : ('T => Unit is Ctl)) : ((Bool, 'T) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="da36b-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="da36b-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="da36b-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="da36b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="da36b-110">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="da36b-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-ctl"></a><span data-ttu-id="da36b-111">Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="da36b-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="da36b-112">Klasik denetim biti doğru ise op olan yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="da36b-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="da36b-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="da36b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="da36b-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="da36b-114">'T</span></span>

<span data-ttu-id="da36b-115">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="da36b-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="da36b-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="da36b-116">See Also</span></span>

- [<span data-ttu-id="da36b-117">Microsoft. hisse. Canon. Cdenetimli</span><span class="sxs-lookup"><span data-stu-id="da36b-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)