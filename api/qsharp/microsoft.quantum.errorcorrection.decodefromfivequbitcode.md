---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromFiveQubitCode
title: Ayrılan Defromfivequbitcode işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromFiveQubitCode
qsharp.summary: Decodes the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 77c5614684f416c7d2e12914ec6246d3ef7098fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201113"
---
# <a name="decodefromfivequbitcode-operation"></a><span data-ttu-id="70b37-102">Ayrılan Defromfivequbitcode işlemi</span><span class="sxs-lookup"><span data-stu-id="70b37-102">DecodeFromFiveQubitCode operation</span></span>

<span data-ttu-id="70b37-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="70b37-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="70b37-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70b37-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70b37-105">⟦ 5, 1, 3 ⟧ hisse kodu kodunu çözer.</span><span class="sxs-lookup"><span data-stu-id="70b37-105">Decodes the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
operation DecodeFromFiveQubitCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="70b37-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="70b37-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="70b37-107">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="70b37-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="70b37-108">Kodlanmış 5-qubit kodu mantıksal durumunu temsil eden bir qubits dizisi.</span><span class="sxs-lookup"><span data-stu-id="70b37-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="70b37-109">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="70b37-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="70b37-110">İkinci parametrede yardımcı qubits ile birlikte ilk parametrede kodlanmamış durumu temsil eden bir qubit dizisi 1 uzunluğunda bir dizi.</span><span class="sxs-lookup"><span data-stu-id="70b37-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="70b37-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="70b37-111">See Also</span></span>

- [<span data-ttu-id="70b37-112">Microsoft. hisse. Errordüzeltmesini. FiveQubitCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="70b37-112">Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoder)
- [<span data-ttu-id="70b37-113">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="70b37-113">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)