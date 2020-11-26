---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: 3ded981dc53236a48f1fb8f6ae12e39c17469447
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219456"
---
# <a name="zbits-function"></a><span data-ttu-id="396da-102">ZBits işlevi</span><span class="sxs-lookup"><span data-stu-id="396da-102">ZBits function</span></span>

<span data-ttu-id="396da-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="396da-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="396da-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="396da-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="396da-105">Pauli işleçleri dizisinin Z bitlerini temsil eden bir tamsayı döndürür.</span><span class="sxs-lookup"><span data-stu-id="396da-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="396da-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="396da-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="396da-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="396da-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="396da-108">Bir tamsayı olarak temsil edilecek Pauli işleçleri dizisi.</span><span class="sxs-lookup"><span data-stu-id="396da-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="396da-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="396da-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="396da-110">İkili temsili $ (p_ {62} \, P_ {61} \, \noktalar p_0) $ olan bir tamsayı $x $ \, , burada $p _i = $0, veya ise $p `paulis[i]` `PauliI` `PauliX` = $1 ' dir `paulis[i]` `PauliY` `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="396da-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="396da-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="396da-111">Remarks</span></span>

<span data-ttu-id="396da-112">Dizi uzunluğu 63 ' den büyükse işlev oluşturulur `paulis` .</span><span class="sxs-lookup"><span data-stu-id="396da-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="396da-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="396da-113">See Also</span></span>

- [<span data-ttu-id="396da-114">Microsoft. hisse. bit düzeyinde. Xbit</span><span class="sxs-lookup"><span data-stu-id="396da-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)