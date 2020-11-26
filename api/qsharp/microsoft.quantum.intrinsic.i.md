---
uid: Microsoft.Quantum.Intrinsic.I
title: I işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 5aae7a5e3b5b441829de8f10f4df539ffc374954
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198956"
---
# <a name="i-operation"></a><span data-ttu-id="31cfb-102">I işlemi</span><span class="sxs-lookup"><span data-stu-id="31cfb-102">I operation</span></span>

<span data-ttu-id="31cfb-103">Ad alanı: [Microsoft. hisse. iç](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="31cfb-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="31cfb-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="31cfb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="31cfb-105">Tek bir qubit üzerinde kimlik işlemini (No-Op) gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="31cfb-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="31cfb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="31cfb-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="31cfb-107">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="31cfb-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="31cfb-108">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31cfb-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="31cfb-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="31cfb-109">Remarks</span></span>

<span data-ttu-id="31cfb-110">Bu bir op değildir.</span><span class="sxs-lookup"><span data-stu-id="31cfb-110">This is a no-op.</span></span> <span data-ttu-id="31cfb-111">Bu, tamamlanma için sağlanır ve bazen kimliği bir algoritmadaki çağırmak ya da bir parametre olarak geçirmek yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="31cfb-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>