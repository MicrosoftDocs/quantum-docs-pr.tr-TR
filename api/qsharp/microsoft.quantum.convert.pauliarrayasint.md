---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: Pauliarrayasınt işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224250"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="611ef-102">Pauliarrayasınt işlevi</span><span class="sxs-lookup"><span data-stu-id="611ef-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="611ef-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="611ef-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="611ef-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="611ef-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="611ef-105">Tek qubit Pauli işleçleri dizisi olarak temsil edilen bir multi-qubit Pauli işlecini tamsayı olarak kodlar.</span><span class="sxs-lookup"><span data-stu-id="611ef-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="611ef-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="611ef-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="611ef-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="611ef-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="611ef-108">En fazla 31 tek-qubit Pauli işleçlerinden oluşan dizi.</span><span class="sxs-lookup"><span data-stu-id="611ef-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="611ef-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="611ef-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="611ef-110">Aşağıda açıklandığı gibi benzersiz şekilde tanımlayan bir tamsayı `paulis` .</span><span class="sxs-lookup"><span data-stu-id="611ef-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="611ef-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="611ef-111">Remarks</span></span>

<span data-ttu-id="611ef-112">Her Pauli işleci iki bit kullanılarak kodlanabilir: $ $ \begin{hizalaması} \cıvadone \mapsto 00, \dörtlü X \mapsto 01, \dörtlü Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="611ef-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="611ef-113">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="611ef-113">\end{align} $$</span></span>

<span data-ttu-id="611ef-114">Pauli işleçleri dizisi verildiğinde `[P0, ..., Pn]` , bu işlev, her Pauli işlecinin eşlemelerini büyük endian sırasıyla birleştirerek ikili genişletmeyle biçimlendirilmiş bir tamsayı döndürür `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="611ef-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>