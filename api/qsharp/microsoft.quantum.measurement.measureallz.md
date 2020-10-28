---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726516"
---
# <a name="measureallz-operation"></a><span data-ttu-id="10605-102">MeasureAllZ işlemi</span><span class="sxs-lookup"><span data-stu-id="10605-102">MeasureAllZ operation</span></span>

<span data-ttu-id="10605-103">Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="10605-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="10605-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="10605-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="10605-105">Çiçek bir qubitlerin bir kaydını Pauli Z temelinde ölçer.</span><span class="sxs-lookup"><span data-stu-id="10605-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="10605-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="10605-106">Description</span></span>

<span data-ttu-id="10605-107">Tüm kaydın eşlik düzeyini temsil eden $Z \otimes Z \otimes \cnoktalar \otimes Z $ temelinde bir qubit kaydı ölçer.</span><span class="sxs-lookup"><span data-stu-id="10605-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="10605-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="10605-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="10605-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="10605-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="10605-110">Ölçülecek kayıt.</span><span class="sxs-lookup"><span data-stu-id="10605-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="10605-111">Çıkış: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="10605-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="10605-112">$Z \otimes Z \otimes \ cnoktalar \otimes Z $ ölçmesi sonucu.</span><span class="sxs-lookup"><span data-stu-id="10605-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>