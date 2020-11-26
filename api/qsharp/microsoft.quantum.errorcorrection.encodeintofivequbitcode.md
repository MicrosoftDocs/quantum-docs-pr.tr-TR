---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Encodeıntofivequbitcode işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 70e52b7440dca1fa8761db13d6187cb6bf8c43c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200994"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="19563-102">Encodeıntofivequbitcode işlemi</span><span class="sxs-lookup"><span data-stu-id="19563-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="19563-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="19563-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="19563-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="19563-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="19563-105">⟦ 5, 1, 3 ⟧ hisse koduna kodluyor.</span><span class="sxs-lookup"><span data-stu-id="19563-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="19563-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="19563-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="19563-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="19563-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="19563-108">Kodlanamayan bir durumu temsil eden bir qubit.</span><span class="sxs-lookup"><span data-stu-id="19563-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="19563-109">Bu dizi `Qubit[]` 1 uzunluktadır.</span><span class="sxs-lookup"><span data-stu-id="19563-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="19563-110">Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="19563-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="19563-111">Kodlanmış durumu temsil etmek için kullanılacak yardımcı qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="19563-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="19563-112">Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="19563-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="19563-113">Kodlanmış durumu depolayan türdeki fiziksel qubit dizisi `LogicalRegister` .</span><span class="sxs-lookup"><span data-stu-id="19563-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="19563-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="19563-114">See Also</span></span>

- [<span data-ttu-id="19563-115">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="19563-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)