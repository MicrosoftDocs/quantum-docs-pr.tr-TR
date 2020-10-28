---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Hazırlık yankı işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733218"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="1c8f5-102">Hazırlık yankı işlemi</span><span class="sxs-lookup"><span data-stu-id="1c8f5-102">PrepareChoiState operation</span></span>

<span data-ttu-id="1c8f5-103">Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="1c8f5-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="1c8f5-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c8f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c8f5-105">Belirli bir işlem için CHOI – Jamiłkowski durumunu verilen başvuru ve hedef Yazmaçları üzerine hazırlar.</span><span class="sxs-lookup"><span data-stu-id="1c8f5-105">Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="1c8f5-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1c8f5-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="1c8f5-107">Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c8f5-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1c8f5-108">Choi – Jamiłkowski State $J (\Lambda)/2 ^ N $ olan Operation $ \Lambda $ hazırlanmaktadır; burada $N $, üzerinde işlem gören qubits sayısıdır `op` .</span><span class="sxs-lookup"><span data-stu-id="1c8f5-108">Operation $\Lambda$ whose Choi–Jamiłkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="1c8f5-109">Başvuru: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1c8f5-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1c8f5-110">$ \Ket{00\cnoktalar 0} $ durumunda, öğesinin eylemi için bir başvuru olarak kullanılacak bir qubits kaydı `op` .</span><span class="sxs-lookup"><span data-stu-id="1c8f5-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1c8f5-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1c8f5-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1c8f5-112">Başlangıçta $ \ket{00\cnoktalar 0} $ durumunda olacak şekilde bir qubıts kaydı `op` .</span><span class="sxs-lookup"><span data-stu-id="1c8f5-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c8f5-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c8f5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1c8f5-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="1c8f5-114">Remarks</span></span>

<span data-ttu-id="1c8f5-115">Bir hisse işleminin CHOI – Jamiłkowski State $J (\Lambda) $ $ $ \begin{hizalaması} J (\Lambda) \mathrel{: =} (\cıvaal\otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langta\cıvadone |), \end{hizalaması} $ $ burada $ | olarak tanımlanmıştır. X\rangle \! \rangle $, bir matrisin $X $ 'ın, sütun yığınlama kuralına *vektörleştirmesi* .</span><span class="sxs-lookup"><span data-stu-id="1c8f5-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="1c8f5-116">Bu durumun klasik bir açıklamasını öğrenmek, $ \Lambda $ ' ın rastgele giriş durumlarına göre hareket etmesinin yanı sıra *hisse işleme* temelini oluşturur.</span><span class="sxs-lookup"><span data-stu-id="1c8f5-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography* .</span></span>

## <a name="see-also"></a><span data-ttu-id="1c8f5-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1c8f5-117">See Also</span></span>

- [<span data-ttu-id="1c8f5-118">Microsoft. hisse. hazırlık. hazırlık yankı Istatea</span><span class="sxs-lookup"><span data-stu-id="1c8f5-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="1c8f5-119">Microsoft. hisse. hazırlık. hazırlık yankı Istatec</span><span class="sxs-lookup"><span data-stu-id="1c8f5-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="1c8f5-120">Microsoft. hisse. hazırlık. hazırlık yankı Istateca</span><span class="sxs-lookup"><span data-stu-id="1c8f5-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)