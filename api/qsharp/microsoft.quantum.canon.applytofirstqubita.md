---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitA
title: ApplyToFirstQubitA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitA
qsharp.summary: Applies an operation to the first qubit in the register. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 00dbff0b562f90653c8569589e838f11e6c938e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729228"
---
# <a name="applytofirstqubita-operation"></a><span data-ttu-id="dfed7-102">ApplyToFirstQubitA işlemi</span><span class="sxs-lookup"><span data-stu-id="dfed7-102">ApplyToFirstQubitA operation</span></span>

<span data-ttu-id="dfed7-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dfed7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dfed7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dfed7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dfed7-105">Kayıttaki ilk qubit 'e bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="dfed7-105">Applies an operation to the first qubit in the register.</span></span>
<span data-ttu-id="dfed7-106">Değiştirici, `A` işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="dfed7-106">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
operation ApplyToFirstQubitA (op : (Qubit => Unit is Adj), register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="dfed7-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="dfed7-107">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="dfed7-108">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama</span><span class="sxs-lookup"><span data-stu-id="dfed7-108">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="dfed7-109">İlk qubit 'e uygulanacak bir işlem</span><span class="sxs-lookup"><span data-stu-id="dfed7-109">An operation to be applied to the first qubit</span></span>


### <a name="register--qubit"></a><span data-ttu-id="dfed7-110">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dfed7-110">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dfed7-111">İşlemin uygulandığı ilk qubit dizisine qubit dizisi</span><span class="sxs-lookup"><span data-stu-id="dfed7-111">Qubit array to the first qubit of which the operation is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="dfed7-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dfed7-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="dfed7-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dfed7-113">See Also</span></span>

- [<span data-ttu-id="dfed7-114">Microsoft. hisse. Canon. ApplyToFirstQubit</span><span class="sxs-lookup"><span data-stu-id="dfed7-114">Microsoft.Quantum.Canon.ApplyToFirstQubit</span></span>](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)