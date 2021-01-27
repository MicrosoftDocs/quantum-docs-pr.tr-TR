---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Measureıdentity işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851818"
---
# <a name="measureidentity-operation"></a><span data-ttu-id="0a8ad-102">Measureıdentity işlemi</span><span class="sxs-lookup"><span data-stu-id="0a8ad-102">MeasureIdentity operation</span></span>

<span data-ttu-id="0a8ad-103">Ad alanı: [Microsoft. hisse. karakterleştirme](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="0a8ad-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="0a8ad-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a8ad-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a8ad-105">Qubits 'in bir kaydındaki kimlik işlecini ölçer.</span><span class="sxs-lookup"><span data-stu-id="0a8ad-105">Measures the identity operator on a register of qubits.</span></span>

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="0a8ad-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0a8ad-106">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="0a8ad-107">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0a8ad-107">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0a8ad-108">Ölçülecek kayıt.</span><span class="sxs-lookup"><span data-stu-id="0a8ad-108">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="0a8ad-109">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="0a8ad-109">Output : __invalid<Result>__</span></span>

<span data-ttu-id="0a8ad-110">Sonuç değeri `Zero` .</span><span class="sxs-lookup"><span data-stu-id="0a8ad-110">The result value `Zero`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a8ad-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0a8ad-111">Remarks</span></span>

<span data-ttu-id="0a8ad-112">$ \Cıvadone $ yalnızca eigenvalue $1 $ olduğundan ve negatif bir eigenvalue olmadığından, bu işlem her zaman `Zero` , eigenvalue $ + 1 = (-1) ^ 0 $ öğesine karşılık gelir ve durumunun daraltımasına neden olmaz `register` .</span><span class="sxs-lookup"><span data-stu-id="0a8ad-112">Since $\boldone$ has only the eigenvalue $1$, and does not have a negative eigenvalue, this operation always returns `Zero`, corresponding to the eigenvalue $+1 = (-1)^0$, and does not cause a collapse of the state of `register`.</span></span>

<span data-ttu-id="0a8ad-113">Bu işlem, kendi kendine yararlı değildir, ancak bir hisse işleminin izleme koruması hakkında bilgi sağladığından işlem tografı bağlamında faydalıdır.</span><span class="sxs-lookup"><span data-stu-id="0a8ad-113">On its own, this operation is not useful, but is helpful in the context of process tomography, as it provides information about the trace preservation of a quantum process.</span></span>
<span data-ttu-id="0a8ad-114">Özellikle, kayıplı ölçeli bir hedef makine, bu işlemi $ \cıvadone $ gerçek ölçimiyle değiştirecek.</span><span class="sxs-lookup"><span data-stu-id="0a8ad-114">In particular, a target machine with lossy measurement should replace this operation by an actual measurement of $\boldone$.</span></span>