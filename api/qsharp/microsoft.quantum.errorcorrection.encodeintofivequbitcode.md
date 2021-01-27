---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoFiveQubitCode
title: Encodeıntofivequbitcode işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoFiveQubitCode
qsharp.summary: Encodes into the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 1bccf46453ad34199dcebc5bcff693359fe2254c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826316"
---
# <a name="encodeintofivequbitcode-operation"></a><span data-ttu-id="f42c1-102">Encodeıntofivequbitcode işlemi</span><span class="sxs-lookup"><span data-stu-id="f42c1-102">EncodeIntoFiveQubitCode operation</span></span>

<span data-ttu-id="f42c1-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f42c1-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f42c1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f42c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f42c1-105">⟦ 5, 1, 3 ⟧ hisse koduna kodluyor.</span><span class="sxs-lookup"><span data-stu-id="f42c1-105">Encodes into the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation EncodeIntoFiveQubitCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="f42c1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f42c1-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="f42c1-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f42c1-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f42c1-108">Kodlanamayan bir durumu temsil eden bir qubit.</span><span class="sxs-lookup"><span data-stu-id="f42c1-108">A qubit representing an unencoded state.</span></span> <span data-ttu-id="f42c1-109">Bu dizi `Qubit[]` 1 uzunluktadır.</span><span class="sxs-lookup"><span data-stu-id="f42c1-109">This array `Qubit[]` is of length 1.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="f42c1-110">Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f42c1-110">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f42c1-111">Kodlanmış durumu temsil etmek için kullanılacak yardımcı qubit kaydı.</span><span class="sxs-lookup"><span data-stu-id="f42c1-111">A register of auxiliary qubits that will be used to represent the encoded state.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="f42c1-112">Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="f42c1-112">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="f42c1-113">Kodlanmış durumu depolayan türdeki fiziksel qubit dizisi `LogicalRegister` .</span><span class="sxs-lookup"><span data-stu-id="f42c1-113">An array of physical qubits of type `LogicalRegister` that store the encoded state.</span></span>

## <a name="see-also"></a><span data-ttu-id="f42c1-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f42c1-114">See Also</span></span>

- [<span data-ttu-id="f42c1-115">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="f42c1-115">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)