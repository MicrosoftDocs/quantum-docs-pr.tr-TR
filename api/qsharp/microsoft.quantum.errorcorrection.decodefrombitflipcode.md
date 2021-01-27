---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Ayrışdefrombitflipcode işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b16e84340053b6c1eab7b91ed8db0461b9eac98e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827555"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="dbb6c-102">Ayrışdefrombitflipcode işlemi</span><span class="sxs-lookup"><span data-stu-id="dbb6c-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="dbb6c-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="dbb6c-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="dbb6c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbb6c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbb6c-105">[3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-ters çevirme kodunun kodunu çözer.</span><span class="sxs-lookup"><span data-stu-id="dbb6c-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="dbb6c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="dbb6c-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="dbb6c-107">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="dbb6c-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="dbb6c-108">Bit çevirme kodunun kod bloğu.</span><span class="sxs-lookup"><span data-stu-id="dbb6c-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="dbb6c-109">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="dbb6c-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="dbb6c-110">Mantıksal yazmaç içinde kodlanan verilerin bir kayıt düzeni ve Syndrome 'yi temsil etmek için kullanılan yardımcı qubits.</span><span class="sxs-lookup"><span data-stu-id="dbb6c-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="dbb6c-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="dbb6c-111">See Also</span></span>

- [<span data-ttu-id="dbb6c-112">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="dbb6c-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="dbb6c-113">Microsoft. hisse. Errordüzeltmesini. Encodeıntobitflipcode</span><span class="sxs-lookup"><span data-stu-id="dbb6c-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)