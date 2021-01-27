---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Sıfırlama işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818638"
---
# <a name="reset-operation"></a><span data-ttu-id="23ea2-102">Sıfırlama işlemi</span><span class="sxs-lookup"><span data-stu-id="23ea2-102">Reset operation</span></span>

<span data-ttu-id="23ea2-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="23ea2-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="23ea2-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="23ea2-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="23ea2-105">Tek bir qubit verildiğinde, bunu ölçer ve güvenli bir şekilde yayımlanabilmesi için | 0 ⟩ durumunda olduğundan emin olun.</span><span class="sxs-lookup"><span data-stu-id="23ea2-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="23ea2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="23ea2-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="23ea2-107">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="23ea2-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="23ea2-108">Durumu $ \ket $ olarak sıfırlanacak olan qubit {0} .</span><span class="sxs-lookup"><span data-stu-id="23ea2-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="23ea2-109">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23ea2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

