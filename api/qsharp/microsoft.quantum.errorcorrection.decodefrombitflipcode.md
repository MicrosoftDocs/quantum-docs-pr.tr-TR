---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromBitFlipCode
title: Ayrışdefrombitflipcode işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromBitFlipCode
qsharp.summary: Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: be6ad5fce9eeb3eea031ff301b78dbb3680b66f0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727121"
---
# <a name="decodefrombitflipcode-operation"></a><span data-ttu-id="44f86-102">Ayrışdefrombitflipcode işlemi</span><span class="sxs-lookup"><span data-stu-id="44f86-102">DecodeFromBitFlipCode operation</span></span>

<span data-ttu-id="44f86-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="44f86-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="44f86-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="44f86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="44f86-105">[3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-ters çevirme kodunun kodunu çözer.</span><span class="sxs-lookup"><span data-stu-id="44f86-105">Decodes from the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation DecodeFromBitFlipCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="44f86-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="44f86-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="44f86-107">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="44f86-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="44f86-108">Bit çevirme kodunun kod bloğu.</span><span class="sxs-lookup"><span data-stu-id="44f86-108">A code block of the bit-flip code.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="44f86-109">Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="44f86-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="44f86-110">Mantıksal yazmaç içinde kodlanan verilerin bir kayıt düzeni ve Syndrome 'yi temsil etmek için kullanılan yardımcı qubits.</span><span class="sxs-lookup"><span data-stu-id="44f86-110">A tuple of the data encoded into the logical register, and the auxiliary qubits used to represent the syndrome.</span></span>

## <a name="see-also"></a><span data-ttu-id="44f86-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="44f86-111">See Also</span></span>

- [<span data-ttu-id="44f86-112">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="44f86-112">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="44f86-113">Microsoft. hisse. Errordüzeltmesini. Encodeıntobitflipcode</span><span class="sxs-lookup"><span data-stu-id="44f86-113">Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode</span></span>](xref:Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode)