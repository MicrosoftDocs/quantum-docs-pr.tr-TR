---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: 7f42d9cab2f80f8f826ad1268b050134f0540cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218232"
---
# <a name="applypauli-operation"></a><span data-ttu-id="45961-102">ApplyPauli işlemi</span><span class="sxs-lookup"><span data-stu-id="45961-102">ApplyPauli operation</span></span>

<span data-ttu-id="45961-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="45961-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="45961-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45961-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45961-105">Multi-qubit Pauli operatörü verildiğinde, kayda karşılık gelen işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="45961-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="45961-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="45961-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="45961-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="45961-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="45961-108">Tek qubit Pauli işleçleri dizisi olarak temsil edilen bir multi-qubit Pauli işleci.</span><span class="sxs-lookup"><span data-stu-id="45961-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="45961-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="45961-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="45961-110">Verilen Pauli işlemini üzerine uygulamak için kaydolun.</span><span class="sxs-lookup"><span data-stu-id="45961-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="45961-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45961-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

