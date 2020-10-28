---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: Pauliarrayasınt işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727500"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="890ab-102">Pauliarrayasınt işlevi</span><span class="sxs-lookup"><span data-stu-id="890ab-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="890ab-103">Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="890ab-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="890ab-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="890ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="890ab-105">Tek qubit Pauli işleçleri dizisi olarak temsil edilen bir multi-qubit Pauli işlecini tamsayı olarak kodlar.</span><span class="sxs-lookup"><span data-stu-id="890ab-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="890ab-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="890ab-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="890ab-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="890ab-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="890ab-108">En fazla 31 tek-qubit Pauli işleçlerinden oluşan dizi.</span><span class="sxs-lookup"><span data-stu-id="890ab-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="890ab-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="890ab-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="890ab-110">Aşağıda açıklandığı gibi benzersiz şekilde tanımlayan bir tamsayı `paulis` .</span><span class="sxs-lookup"><span data-stu-id="890ab-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="890ab-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="890ab-111">Remarks</span></span>

<span data-ttu-id="890ab-112">Her Pauli işleci iki bit kullanılarak kodlanabilir: $ $ \begin{hizalaması} \cıvadone \mapsto 00, \dörtlü X \mapsto 01, \dörtlü Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="890ab-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="890ab-113">\end{hizalaması} $ $</span><span class="sxs-lookup"><span data-stu-id="890ab-113">\end{align} $$</span></span>

<span data-ttu-id="890ab-114">Pauli işleçleri dizisi verildiğinde `[P0, ..., Pn]` , bu işlev, her Pauli işlecinin eşlemelerini büyük endian sırasıyla birleştirerek ikili genişletmeyle biçimlendirilmiş bir tamsayı döndürür `bits(Pn) ... bits(P0)` .</span><span class="sxs-lookup"><span data-stu-id="890ab-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>