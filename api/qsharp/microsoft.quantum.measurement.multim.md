---
uid: Microsoft.Quantum.Measurement.MultiM
title: Çoklu çalışma işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227004"
---
# <a name="multim-operation"></a><span data-ttu-id="ef91e-102">Çoklu çalışma işlemi</span><span class="sxs-lookup"><span data-stu-id="ef91e-102">MultiM operation</span></span>

<span data-ttu-id="ef91e-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="ef91e-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="ef91e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef91e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef91e-105">Belirli bir dizide her bir qubit ' i standart temelinde ölçer.</span><span class="sxs-lookup"><span data-stu-id="ef91e-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="ef91e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="ef91e-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="ef91e-107">hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ef91e-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ef91e-108">Ölçülecek bir qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="ef91e-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ef91e-109">Çıkış: __geçersiz <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="ef91e-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="ef91e-110">Ölçüm sonuçları dizisi.</span><span class="sxs-lookup"><span data-stu-id="ef91e-110">An array of measurement results.</span></span>