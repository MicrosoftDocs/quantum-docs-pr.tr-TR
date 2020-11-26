---
uid: Microsoft.Quantum.Diagnostics.DumpReferenceAndTarget
title: DumpReferenceAndTarget işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpReferenceAndTarget
qsharp.summary: Uses DumpRegister to provide diagnostics on the state of a reference and target register. Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.
ms.openlocfilehash: ef7e59b1561be04cba5839ebc397702b6c1df5bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202048"
---
# <a name="dumpreferenceandtarget-operation"></a><span data-ttu-id="18ea6-102">DumpReferenceAndTarget işlemi</span><span class="sxs-lookup"><span data-stu-id="18ea6-102">DumpReferenceAndTarget operation</span></span>

<span data-ttu-id="18ea6-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="18ea6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="18ea6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="18ea6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="18ea6-105">Bir başvuru ve hedef kayıt durumunda tanılama sağlamak için DumpRegister kullanır.</span><span class="sxs-lookup"><span data-stu-id="18ea6-105">Uses DumpRegister to provide diagnostics on the state of a reference and target register.</span></span> <span data-ttu-id="18ea6-106">Tek bir Birleşik kayıt yerine ayrı kayıt olarak geçersiz kılma ve yorumlama sağlamak için ayrı bir işlem olarak yazılmıştır.</span><span class="sxs-lookup"><span data-stu-id="18ea6-106">Written as separate operation to allow overriding and interpreting as separate registers, rather than as a single combined register.</span></span>

```qsharp
operation DumpReferenceAndTarget (reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="18ea6-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="18ea6-107">Input</span></span>

### <a name="reference--qubit"></a><span data-ttu-id="18ea6-108">Başvuru: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="18ea6-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="18ea6-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="18ea6-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="18ea6-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="18ea6-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

