---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: Hazırlık Yankııteca işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: b9d2cdaea1ebc957719d92bf12901c54a55a56aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725819"
---
# <a name="preparechoistateca-operation"></a><span data-ttu-id="a2b33-102">Hazırlık Yankııteca işlemi</span><span class="sxs-lookup"><span data-stu-id="a2b33-102">PrepareChoiStateCA operation</span></span>

<span data-ttu-id="a2b33-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a2b33-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a2b33-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2b33-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2b33-105">Belirtilen başvuru ve hedef Yazmaçları üzerinde hem denetimli hem de adjoint türevlerine sahip belirli bir işlem için CHOI – Jamiłkowski durumunu hazırlar.</span><span class="sxs-lookup"><span data-stu-id="a2b33-105">Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a2b33-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a2b33-106">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="a2b33-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="a2b33-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="a2b33-108">Başvuru: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a2b33-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="a2b33-109">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a2b33-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="a2b33-110">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2b33-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a2b33-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a2b33-111">See Also</span></span>

- [<span data-ttu-id="a2b33-112">Microsoft. hisse. hazırlık. hazırlık yankı IState</span><span class="sxs-lookup"><span data-stu-id="a2b33-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)