---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 740461ee17bdda281a6bd8572a15d27b17be9535
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840964"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="6075c-102">CControlledCA işlevi</span><span class="sxs-lookup"><span data-stu-id="6075c-102">CControlledCA function</span></span>

<span data-ttu-id="6075c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6075c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6075c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6075c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6075c-105">Bir işlem işlemi verildiğinde, bir klasik denetim biti doğru ise op 'yi uygulayan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="6075c-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="6075c-106">Yoksa `false` , hiçbir şey olmaz.</span><span class="sxs-lookup"><span data-stu-id="6075c-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="6075c-107">Değiştirici, `CA` işlemin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="6075c-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="6075c-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="6075c-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="6075c-109">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="6075c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6075c-110">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="6075c-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj--ctl"></a><span data-ttu-id="6075c-111">Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="6075c-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6075c-112">Klasik denetim biti doğru ise op olan yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="6075c-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6075c-113">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6075c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6075c-114">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6075c-114">'T</span></span>

<span data-ttu-id="6075c-115">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="6075c-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6075c-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6075c-116">See Also</span></span>

- [<span data-ttu-id="6075c-117">Microsoft. hisse. Canon. Cdenetimli</span><span class="sxs-lookup"><span data-stu-id="6075c-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)