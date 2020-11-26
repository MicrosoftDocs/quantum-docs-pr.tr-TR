---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bc2b1275b4258b9cc2db45c9e5cfe14f7eee0c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208814"
---
# <a name="applytofirstqubitca-operation"></a><span data-ttu-id="38749-102">ApplyToFirstQubitCA işlemi</span><span class="sxs-lookup"><span data-stu-id="38749-102">ApplyToFirstQubitCA operation</span></span>

<span data-ttu-id="38749-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="38749-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="38749-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38749-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38749-105">Kayıttaki ilk qubit 'e işlem işleci uygular.</span><span class="sxs-lookup"><span data-stu-id="38749-105">Applies operation op to the first qubit in the register.</span></span>
<span data-ttu-id="38749-106">Değiştirici, `CA` işlemin denetlenebilir ve adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="38749-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="38749-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="38749-107">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="38749-108">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="38749-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="38749-109">İlk qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="38749-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="38749-110">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="38749-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="38749-111">İşlemin uygulandığı ilk qubit dizisine qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="38749-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="38749-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="38749-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="38749-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="38749-113">See Also</span></span>

- [<span data-ttu-id="38749-114">Microsoft. hisse. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="38749-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)