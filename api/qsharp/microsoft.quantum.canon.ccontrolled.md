---
uid: Microsoft.Quantum.Canon.CControlled
title: Cdenetlenen işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: f4d91471eae859b7018c9e7ea0c1c853619c484d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841003"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="4fd0b-102">Cdenetlenen işlevi</span><span class="sxs-lookup"><span data-stu-id="4fd0b-102">CControlled function</span></span>

<span data-ttu-id="4fd0b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4fd0b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4fd0b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4fd0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4fd0b-105">Bir işlem işlemi verildiğinde, bir klasik denetim biti doğru ise op 'yi uygulayan yeni bir işlem döndürür.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="4fd0b-106">Yoksa `false` , hiçbir şey olmaz.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="4fd0b-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="4fd0b-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4fd0b-108">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fd0b-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4fd0b-109">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="4fd0b-110">Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fd0b-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4fd0b-111">Klasik denetim biti doğru ise op olan yeni bir işlem.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4fd0b-112">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="4fd0b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4fd0b-113">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="4fd0b-113">'T</span></span>

<span data-ttu-id="4fd0b-114">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fd0b-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4fd0b-115">See Also</span></span>

- [<span data-ttu-id="4fd0b-116">Microsoft. hisse. Canon. CControlledC</span><span class="sxs-lookup"><span data-stu-id="4fd0b-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="4fd0b-117">Microsoft. hisse. Canon. Ccontroltada</span><span class="sxs-lookup"><span data-stu-id="4fd0b-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="4fd0b-118">Microsoft. hisse. Canon. CControlledCA</span><span class="sxs-lookup"><span data-stu-id="4fd0b-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)