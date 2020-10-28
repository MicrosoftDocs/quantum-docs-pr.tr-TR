---
uid: Microsoft.Quantum.Measurement.MultiM
title: Çoklu çalışma işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726503"
---
# <a name="multim-operation"></a><span data-ttu-id="26bde-102">Çoklu çalışma işlemi</span><span class="sxs-lookup"><span data-stu-id="26bde-102">MultiM operation</span></span>

<span data-ttu-id="26bde-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="26bde-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="26bde-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26bde-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26bde-105">Belirli bir dizide her bir qubit ' i standart temelinde ölçer.</span><span class="sxs-lookup"><span data-stu-id="26bde-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="26bde-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="26bde-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="26bde-107">hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="26bde-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="26bde-108">Ölçülecek bir qubit dizisi.</span><span class="sxs-lookup"><span data-stu-id="26bde-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="26bde-109">Çıkış: __geçersiz <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="26bde-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="26bde-110">Ölçüm sonuçları dizisi.</span><span class="sxs-lookup"><span data-stu-id="26bde-110">An array of measurement results.</span></span>