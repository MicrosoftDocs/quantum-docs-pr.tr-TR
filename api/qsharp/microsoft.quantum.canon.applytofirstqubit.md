---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubit
title: ApplyToFirstQubit işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubit
qsharp.summary: Applies an operation to the first qubit in the register.
ms.openlocfilehash: 381f8d689fba1984ba7fa287d658578bd5b6c48c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850724"
---
# <a name="applytofirstqubit-operation"></a><span data-ttu-id="c4bf5-102">ApplyToFirstQubit işlemi</span><span class="sxs-lookup"><span data-stu-id="c4bf5-102">ApplyToFirstQubit operation</span></span>

<span data-ttu-id="c4bf5-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4bf5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4bf5-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c4bf5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c4bf5-105">Kayıttaki ilk qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="c4bf5-105">Applies an operation to the first qubit in the register.</span></span>

```qsharp
operation ApplyToFirstQubit (op : (Qubit => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c4bf5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c4bf5-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="c4bf5-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [birimi](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4bf5-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c4bf5-108">İlk qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="c4bf5-108">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="c4bf5-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c4bf5-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c4bf5-110">İşlemin uygulandığı ilk qubit dizisine qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="c4bf5-110">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4bf5-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4bf5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c4bf5-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c4bf5-112">See Also</span></span>

- [<span data-ttu-id="c4bf5-113">Microsoft. hisse. Canon. ApplyToFirstQubitA</span><span class="sxs-lookup"><span data-stu-id="c4bf5-113">Microsoft.Quantum.Canon.ApplyToFirstQubitA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitA)
- [<span data-ttu-id="c4bf5-114">Microsoft. hisse. Canon. ApplyToFirstQubitC</span><span class="sxs-lookup"><span data-stu-id="c4bf5-114">Microsoft.Quantum.Canon.ApplyToFirstQubitC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitC)
- [<span data-ttu-id="c4bf5-115">Microsoft. hisse. Canon. ApplyToFirstQubitCA</span><span class="sxs-lookup"><span data-stu-id="c4bf5-115">Microsoft.Quantum.Canon.ApplyToFirstQubitCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitCA)