---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 609e937a03bebf45aa9398225bd1b7e2b717807a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843262"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="51fb1-102">CopyMostSignificantBit işlemi</span><span class="sxs-lookup"><span data-stu-id="51fb1-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="51fb1-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="51fb1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="51fb1-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51fb1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51fb1-105">Qubit yazmacın en önemli bitini `from` qubit 'e işaretsiz bir tamsayıyı temsil eder `target` .</span><span class="sxs-lookup"><span data-stu-id="51fb1-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="51fb1-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="51fb1-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="51fb1-107">Kimden: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="51fb1-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="51fb1-108">En yüksek bitin kopyalandığı işaretsiz tamsayı.</span><span class="sxs-lookup"><span data-stu-id="51fb1-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="51fb1-109">tamsayı, küçük endian biçiminde kodlanır.</span><span class="sxs-lookup"><span data-stu-id="51fb1-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="51fb1-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="51fb1-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="51fb1-111">En yüksek bitin kopyalandığı qubit.</span><span class="sxs-lookup"><span data-stu-id="51fb1-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="51fb1-112">Bit kodlaması hesaplama esasıdır.</span><span class="sxs-lookup"><span data-stu-id="51fb1-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="51fb1-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51fb1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="51fb1-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="51fb1-114">See Also</span></span>

- [<span data-ttu-id="51fb1-115">Microsoft. hisse. aritmetik. Litttaendian</span><span class="sxs-lookup"><span data-stu-id="51fb1-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)