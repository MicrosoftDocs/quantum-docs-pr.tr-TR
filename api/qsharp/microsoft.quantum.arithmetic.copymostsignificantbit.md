---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 39a2dc2fe33f46c2767def06a44cde07e2f01497
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223298"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="7d914-102">CopyMostSignificantBit işlemi</span><span class="sxs-lookup"><span data-stu-id="7d914-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="7d914-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7d914-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7d914-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d914-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d914-105">Qubit yazmacın en önemli bitini `from` qubit 'e işaretsiz bir tamsayıyı temsil eder `target` .</span><span class="sxs-lookup"><span data-stu-id="7d914-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="7d914-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7d914-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="7d914-107">Kimden: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7d914-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7d914-108">En yüksek bitin kopyalandığı işaretsiz tamsayı.</span><span class="sxs-lookup"><span data-stu-id="7d914-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="7d914-109">tamsayı, küçük endian biçiminde kodlanır.</span><span class="sxs-lookup"><span data-stu-id="7d914-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7d914-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7d914-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7d914-111">En yüksek bitin kopyalandığı qubit.</span><span class="sxs-lookup"><span data-stu-id="7d914-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="7d914-112">Bit kodlaması hesaplama esasıdır.</span><span class="sxs-lookup"><span data-stu-id="7d914-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d914-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d914-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="7d914-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7d914-114">See Also</span></span>

- [<span data-ttu-id="7d914-115">Microsoft. hisse. aritmetik. Litttaendian</span><span class="sxs-lookup"><span data-stu-id="7d914-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)