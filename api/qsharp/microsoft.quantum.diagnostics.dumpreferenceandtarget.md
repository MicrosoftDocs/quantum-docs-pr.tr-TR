---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: DumpReferenceAndTarget işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: f791f6f1e3c1b1da14ac3548a4bd78bb4f24ff83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727278"
---
# <a name="dumpreferenceandtarget-operation"></a><span data-ttu-id="b05e7-102">DumpReferenceAndTarget işlemi</span><span class="sxs-lookup"><span data-stu-id="b05e7-102">DumpReferenceAndTarget operation</span></span>

<span data-ttu-id="b05e7-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b05e7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b05e7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b05e7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b05e7-105">Bir başvuru ve hedef kayıt durumunda tanılama sağlamak için DumpRegister kullanır.</span><span class="sxs-lookup"><span data-stu-id="b05e7-105">Uses DumpRegister to provide diagnostics on the state of a reference and target register.</span></span> <span data-ttu-id="b05e7-106">Tek bir Birleşik kayıt yerine ayrı kayıt olarak geçersiz kılma ve yorumlama sağlamak için ayrı bir işlem olarak yazılmıştır.</span><span class="sxs-lookup"><span data-stu-id="b05e7-106">Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.</span></span>

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b05e7-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="b05e7-107">Input</span></span>

### <a name="reference--qubit"></a><span data-ttu-id="b05e7-108">Başvuru: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b05e7-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="b05e7-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b05e7-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="b05e7-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b05e7-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
