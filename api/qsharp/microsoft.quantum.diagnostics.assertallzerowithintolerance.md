---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Assertallsıfırlaması Withıntoleranslı işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 281855ec79d280c903ebb4d05614081767840778
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830863"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="0d9d0-102">Assertallsıfırlaması Withıntoleranslı işlemi</span><span class="sxs-lookup"><span data-stu-id="0d9d0-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="0d9d0-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0d9d0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0d9d0-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0d9d0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0d9d0-105">Verilen qubits 'in, {0} belirli bir toleranstan kadar $ \gre$ durumunda olduğu onay.</span><span class="sxs-lookup"><span data-stu-id="0d9d0-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="0d9d0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0d9d0-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="0d9d0-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0d9d0-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0d9d0-108">$ \ Ayraç $ durumunda olmak üzere onaylanan qubits {0} .</span><span class="sxs-lookup"><span data-stu-id="0d9d0-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="0d9d0-109">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0d9d0-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0d9d0-110">Durumun $ \ket $ durumunda olması gereken doğruluk {0}</span><span class="sxs-lookup"><span data-stu-id="0d9d0-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d9d0-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d9d0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="0d9d0-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0d9d0-112">See Also</span></span>

- [<span data-ttu-id="0d9d0-113">Microsoft. hisse. Diagnostics. Assertqubitwithıntoleransı</span><span class="sxs-lookup"><span data-stu-id="0d9d0-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)