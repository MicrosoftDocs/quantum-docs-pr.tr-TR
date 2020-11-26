---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 4f0b209988c01076bdd0429d36d98c8060141618
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208848"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="709ea-102">ApplyToFirstQubitA işlemi</span><span class="sxs-lookup"><span data-stu-id="709ea-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="709ea-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="709ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="709ea-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="709ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="709ea-105">Kayıttaki ilk qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="709ea-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="709ea-106">Değiştirici, `A` işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="709ea-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="709ea-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="709ea-107">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="709ea-108">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="709ea-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="709ea-109">İlk qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="709ea-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="709ea-110">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="709ea-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="709ea-111">İşlemin uygulandığı ilk qubit dizisine qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="709ea-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="709ea-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="709ea-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="709ea-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="709ea-113">See Also</span></span>

- [<span data-ttu-id="709ea-114">Microsoft. hisse. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="709ea-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)