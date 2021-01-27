---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854680"
---
# <a name="measureallz-operation"></a><span data-ttu-id="31471-102">MeasureAllZ işlemi</span><span class="sxs-lookup"><span data-stu-id="31471-102">MeasureAllZ operation</span></span>

<span data-ttu-id="31471-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="31471-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="31471-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31471-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31471-105">Çiçek bir qubitlerin bir kaydını Pauli Z temelinde ölçer.</span><span class="sxs-lookup"><span data-stu-id="31471-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="31471-106">Description</span><span class="sxs-lookup"><span data-stu-id="31471-106">Description</span></span>

<span data-ttu-id="31471-107">Tüm kaydın eşlik düzeyini temsil eden $Z \otimes Z \otimes \cnoktalar \otimes Z $ temelinde bir qubit kaydı ölçer.</span><span class="sxs-lookup"><span data-stu-id="31471-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="31471-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="31471-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="31471-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="31471-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="31471-110">Ölçülecek kayıt.</span><span class="sxs-lookup"><span data-stu-id="31471-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="31471-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="31471-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="31471-112">$Z \otimes Z \otimes \ cnoktalar \otimes Z $ ölçmesi sonucu.</span><span class="sxs-lookup"><span data-stu-id="31471-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>