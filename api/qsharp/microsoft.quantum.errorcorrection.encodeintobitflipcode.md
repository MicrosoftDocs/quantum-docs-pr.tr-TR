---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Encodeıntobitflipcode işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: b27759caba3c5dd363dbdf24d6e5de76870173cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200960"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="cc08a-102">Encodeıntobitflipcode işlemi</span><span class="sxs-lookup"><span data-stu-id="cc08a-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="cc08a-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="cc08a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="cc08a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc08a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc08a-105">[3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-ters çevirme koduna kodluyor.</span><span class="sxs-lookup"><span data-stu-id="cc08a-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="cc08a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="cc08a-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="cc08a-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cc08a-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cc08a-108">Korunacak verileri temsil eden fiziksel qubits kaydı.</span><span class="sxs-lookup"><span data-stu-id="cc08a-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="cc08a-109">Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cc08a-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cc08a-110">Başlangıçta $ \ket {00} $ durumunda korunan verileri kodlamada kullanılacak bir yardımcı qubits kaydı.</span><span class="sxs-lookup"><span data-stu-id="cc08a-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="cc08a-111">Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="cc08a-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="cc08a-112">Kodlama sırasında kullanılan fiziksel ve yardımcı qubit, mantıksal kayıt olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="cc08a-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc08a-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cc08a-113">See Also</span></span>

- [<span data-ttu-id="cc08a-114">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="cc08a-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)