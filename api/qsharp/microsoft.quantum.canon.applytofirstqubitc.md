---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 2659c3a97baa68cb4c1d7781381f89742902594d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217518"
---
# <a name="applytofirstqubitc-operation"></a><span data-ttu-id="4d82d-102">ApplyToFirstQubitC işlemi</span><span class="sxs-lookup"><span data-stu-id="4d82d-102">ApplyToFirstQubitC operation</span></span>

<span data-ttu-id="4d82d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4d82d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4d82d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d82d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d82d-105">Kayıttaki ilk qubit 'e işlem işleci uygular.</span><span class="sxs-lookup"><span data-stu-id="4d82d-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="4d82d-106">Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="4d82d-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="4d82d-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="4d82d-107">Input</span></span>

### <a name="op--qubit--unit--is-ctl"></a><span data-ttu-id="4d82d-108">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [birimi](xref:microsoft.quantum.lang-ref.unit)  CTL 'dir</span><span class="sxs-lookup"><span data-stu-id="4d82d-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4d82d-109">İlk qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="4d82d-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="4d82d-110">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4d82d-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4d82d-111">İşlemin uygulandığı ilk qubit dizisine qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="4d82d-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d82d-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d82d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4d82d-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4d82d-113">See Also</span></span>

- [<span data-ttu-id="4d82d-114">Microsoft. hisse. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="4d82d-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)