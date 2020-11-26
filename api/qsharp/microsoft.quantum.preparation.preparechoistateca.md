---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: Hazırlık Yankııteca işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: abe75865149c985426a5eaf69cf41433829e1916
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210497"
---
# <a name="preparechoistateca-operation"></a><span data-ttu-id="4f2a6-102">Hazırlık Yankııteca işlemi</span><span class="sxs-lookup"><span data-stu-id="4f2a6-102">PrepareChoiStateCA operation</span></span>

<span data-ttu-id="4f2a6-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="4f2a6-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="4f2a6-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f2a6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f2a6-105">Belirtilen başvuru ve hedef Yazmaçları üzerinde hem denetimli hem de adjoint türevlerine sahip belirli bir işlem için CHOI – Jamiołkowski durumunu hazırlar.</span><span class="sxs-lookup"><span data-stu-id="4f2a6-105">Prepares the Choi–Jamiołkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4f2a6-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4f2a6-106">Input</span></span>

### <a name="op--qubit--unit--is-adj--ctl"></a><span data-ttu-id="4f2a6-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL</span><span class="sxs-lookup"><span data-stu-id="4f2a6-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="4f2a6-108">Başvuru: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4f2a6-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="4f2a6-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4f2a6-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="4f2a6-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f2a6-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="4f2a6-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4f2a6-111">See Also</span></span>

- [<span data-ttu-id="4f2a6-112">Microsoft. hisse. hazırlık. hazırlık yankı IState</span><span class="sxs-lookup"><span data-stu-id="4f2a6-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)