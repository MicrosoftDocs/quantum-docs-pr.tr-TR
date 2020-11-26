---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227089"
---
# <a name="measureallz-operation"></a><span data-ttu-id="da451-102">MeasureAllZ işlemi</span><span class="sxs-lookup"><span data-stu-id="da451-102">MeasureAllZ operation</span></span>

<span data-ttu-id="da451-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="da451-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="da451-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da451-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da451-105">Çiçek bir qubitlerin bir kaydını Pauli Z temelinde ölçer.</span><span class="sxs-lookup"><span data-stu-id="da451-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="da451-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="da451-106">Description</span></span>

<span data-ttu-id="da451-107">Tüm kaydın eşlik düzeyini temsil eden $Z \otimes Z \otimes \cnoktalar \otimes Z $ temelinde bir qubit kaydı ölçer.</span><span class="sxs-lookup"><span data-stu-id="da451-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="da451-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="da451-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="da451-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="da451-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="da451-110">Ölçülecek kayıt.</span><span class="sxs-lookup"><span data-stu-id="da451-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="da451-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="da451-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="da451-112">$Z \otimes Z \otimes \ cnoktalar \otimes Z $ ölçmesi sonucu.</span><span class="sxs-lookup"><span data-stu-id="da451-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>