---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Ayrılan Defromfivequbitcode işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 421da6296b604f30aefed58730091f64f19c3a61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727115"
---
# <a name="decodefromfivequbitcode-operation"></a><span data-ttu-id="37c52-102">Ayrılan Defromfivequbitcode işlemi</span><span class="sxs-lookup"><span data-stu-id="37c52-102">DecodeFromFiveQubitCode operation</span></span>

<span data-ttu-id="37c52-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="37c52-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="37c52-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37c52-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37c52-105">⟦ 5, 1, 3 ⟧ hisse kodu kodunu çözer.</span><span class="sxs-lookup"><span data-stu-id="37c52-105">Decodes the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="37c52-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="37c52-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="37c52-107">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="37c52-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="37c52-108">Kodlanmış 5-qubit kodu mantıksal durumunu temsil eden bir qubits dizisi.</span><span class="sxs-lookup"><span data-stu-id="37c52-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="37c52-109">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="37c52-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="37c52-110">İkinci parametrede yardımcı qubits ile birlikte ilk parametrede kodlanmamış durumu temsil eden bir qubit dizisi 1 uzunluğunda bir dizi.</span><span class="sxs-lookup"><span data-stu-id="37c52-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="37c52-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="37c52-111">See Also</span></span>

- [<span data-ttu-id="37c52-112">Microsoft. hisse. Errordüzeltmesini. FiveQubitCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="37c52-112">Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [<span data-ttu-id="37c52-113">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="37c52-113">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)