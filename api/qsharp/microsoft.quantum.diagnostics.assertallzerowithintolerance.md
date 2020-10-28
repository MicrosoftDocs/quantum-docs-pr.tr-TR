---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: Assertallsıfırlaması Withıntoleranslı işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727361"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="1f44d-102">Assertallsıfırlaması Withıntoleranslı işlemi</span><span class="sxs-lookup"><span data-stu-id="1f44d-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="1f44d-103">Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1f44d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1f44d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f44d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f44d-105">Verilen qubits 'in, {0} belirli bir toleranstan kadar $ \gre$ durumunda olduğu onay.</span><span class="sxs-lookup"><span data-stu-id="1f44d-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="1f44d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1f44d-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="1f44d-107">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f44d-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f44d-108">$ \ Ayraç $ durumunda olmak üzere onaylanan qubits {0} .</span><span class="sxs-lookup"><span data-stu-id="1f44d-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="1f44d-109">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1f44d-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1f44d-110">Durumun $ \ket $ durumunda olması gereken doğruluk {0}</span><span class="sxs-lookup"><span data-stu-id="1f44d-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f44d-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f44d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="1f44d-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1f44d-112">See Also</span></span>

- [<span data-ttu-id="1f44d-113">Microsoft. hisse. Diagnostics. Assertqubitwithıntoleransı</span><span class="sxs-lookup"><span data-stu-id="1f44d-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)