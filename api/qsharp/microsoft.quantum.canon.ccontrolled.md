---
uid: Microsoft.Quantum.Canon.CControlled
title: Cdenetlenen işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: 76e663e9a4b53c7ed74a1b70da516fb07958923b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216906"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="6b9a9-102">Cdenetlenen işlevi</span><span class="sxs-lookup"><span data-stu-id="6b9a9-102">CControlled function</span></span>

<span data-ttu-id="6b9a9-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b9a9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b9a9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b9a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b9a9-105">Bir işlem işlemi verildiğinde, bir klasik denetim biti doğru ise op 'yi uygulayan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="6b9a9-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="6b9a9-106">Yoksa `false` , hiçbir şey olmaz.</span><span class="sxs-lookup"><span data-stu-id="6b9a9-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="6b9a9-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="6b9a9-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="6b9a9-108">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b9a9-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6b9a9-109">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="6b9a9-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="6b9a9-110">Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b9a9-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6b9a9-111">Klasik denetim biti doğru ise op olan yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="6b9a9-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6b9a9-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6b9a9-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b9a9-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6b9a9-113">'T</span></span>

<span data-ttu-id="6b9a9-114">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="6b9a9-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b9a9-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6b9a9-115">See Also</span></span>

- [<span data-ttu-id="6b9a9-116">Microsoft. hisse. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="6b9a9-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="6b9a9-117">Microsoft. hisse. Canon. Ccontroltada</span><span class="sxs-lookup"><span data-stu-id="6b9a9-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="6b9a9-118">Microsoft. hisse. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="6b9a9-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)