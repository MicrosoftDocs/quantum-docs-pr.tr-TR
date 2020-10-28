---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoBitFlipCode
title: Encodeıntobitflipcode işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoBitFlipCode
qsharp.summary: Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.
ms.openlocfilehash: 694d3f7a412b64b0ad533b4478a9274384d05c61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727086"
---
# <a name="encodeintobitflipcode-operation"></a><span data-ttu-id="c120d-102">Encodeıntobitflipcode işlemi</span><span class="sxs-lookup"><span data-stu-id="c120d-102">EncodeIntoBitFlipCode operation</span></span>

<span data-ttu-id="c120d-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c120d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c120d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c120d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c120d-105">[3, 1, 3]/⟦ 3, 1, 1 ⟧ bit-ters çevirme koduna kodluyor.</span><span class="sxs-lookup"><span data-stu-id="c120d-105">Encodes into the [3, 1, 3] / ⟦3, 1, 1⟧ bit-flip code.</span></span>

```qsharp
operation EncodeIntoBitFlipCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a><span data-ttu-id="c120d-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c120d-106">Input</span></span>

### <a name="physregister--qubit"></a><span data-ttu-id="c120d-107">physRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c120d-107">physRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c120d-108">Korunacak verileri temsil eden fiziksel qubits kaydı.</span><span class="sxs-lookup"><span data-stu-id="c120d-108">A register of physical qubits representing the data to be protected.</span></span>


### <a name="auxqubits--qubit"></a><span data-ttu-id="c120d-109">Kequbits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c120d-109">auxQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c120d-110">Başlangıçta $ \ket {00} $ durumunda korunan verileri kodlamada kullanılacak bir yardımcı qubits kaydı.</span><span class="sxs-lookup"><span data-stu-id="c120d-110">A register of auxiliary qubits initially in the $\ket{00}$ state to be used in encoding the data to be protected.</span></span>



## <a name="output--logicalregister"></a><span data-ttu-id="c120d-111">Çıkış: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="c120d-111">Output : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="c120d-112">Kodlama sırasında kullanılan fiziksel ve yardımcı qubit, mantıksal kayıt olarak gösterilir.</span><span class="sxs-lookup"><span data-stu-id="c120d-112">The physical and auxiliary qubits used in encoding, represented as a logical register.</span></span>

## <a name="see-also"></a><span data-ttu-id="c120d-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c120d-113">See Also</span></span>

- [<span data-ttu-id="c120d-114">Microsoft. hisse. Errordüzeltmesini. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="c120d-114">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)