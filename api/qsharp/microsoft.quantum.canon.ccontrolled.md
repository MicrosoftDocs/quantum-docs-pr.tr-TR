---
uid: Microsoft.Quantum.Canon.CControlled
title: Cdenetlenen işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728880"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="e0158-102">Cdenetlenen işlevi</span><span class="sxs-lookup"><span data-stu-id="e0158-102">CControlled function</span></span>

<span data-ttu-id="e0158-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e0158-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e0158-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e0158-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e0158-105">Bir işlem işlemi verildiğinde, bir klasik denetim biti doğru ise op 'yi uygulayan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="e0158-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="e0158-106">Yoksa `false` , hiçbir şey olmaz.</span><span class="sxs-lookup"><span data-stu-id="e0158-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="e0158-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="e0158-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="e0158-108">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0158-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e0158-109">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="e0158-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="e0158-110">Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0158-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e0158-111">Klasik denetim biti doğru ise op olan yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="e0158-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e0158-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="e0158-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e0158-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="e0158-113">'T</span></span>

<span data-ttu-id="e0158-114">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="e0158-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0158-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e0158-115">See Also</span></span>

- [<span data-ttu-id="e0158-116">Microsoft. hisse. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="e0158-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="e0158-117">Microsoft. hisse. Canon. Ccontroltada</span><span class="sxs-lookup"><span data-stu-id="e0158-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="e0158-118">Microsoft. hisse. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="e0158-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)