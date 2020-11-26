---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Measureıdentity işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 4a169355d0669c67f0eb14c80e8554b2f24b035a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216124"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="923a9-102">Measureıdentity işlemi</span><span class="sxs-lookup"><span data-stu-id="923a9-102">MeasureIdentity operation</span></span>

<span data-ttu-id="923a9-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="923a9-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="923a9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="923a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="923a9-105">Qubits 'in bir kaydındaki kimlik işlecini ölçer.</span><span class="sxs-lookup"><span data-stu-id="923a9-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="923a9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="923a9-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="923a9-107">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="923a9-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="923a9-108">Ölçülecek kayıt.</span><span class="sxs-lookup"><span data-stu-id="923a9-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="923a9-109">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="923a9-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="923a9-110">Sonuç değeri `Zero` .</span><span class="sxs-lookup"><span data-stu-id="923a9-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="923a9-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="923a9-111">Remarks</span></span>

<span data-ttu-id="923a9-112">$ \Cıvadone $ yalnızca eigenvalue $1 $ olduğundan ve negatif bir eigenvalue olmadığından, bu işlem her zaman `Zero` , eigenvalue $ + 1 = (-1) ^ 0 $ öğesine karşılık gelir ve durumunun daraltımasına neden olmaz `register` .</span><span class="sxs-lookup"><span data-stu-id="923a9-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="923a9-113">Bu işlem, kendi kendine yararlı değildir, ancak bir hisse işleminin izleme koruması hakkında bilgi sağladığından işlem tografı bağlamında faydalıdır.</span><span class="sxs-lookup"><span data-stu-id="923a9-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="923a9-114">Özellikle, kayıplı ölçeli bir hedef makine, bu işlemi $ \cıvadone $ gerçek ölçimiyle değiştirecek.</span><span class="sxs-lookup"><span data-stu-id="923a9-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>