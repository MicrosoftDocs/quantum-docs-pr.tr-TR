---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: f66b8ef0370e898dd1d095ff2840c91566f32cb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729791"
---
# <a name="zbits-function"></a><span data-ttu-id="f79d2-102">ZBits işlevi</span><span class="sxs-lookup"><span data-stu-id="f79d2-102">ZBits function</span></span>

<span data-ttu-id="f79d2-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="f79d2-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="f79d2-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f79d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f79d2-105">Pauli işleçleri dizisinin Z bitlerini temsil eden bir tamsayı döndürür.</span><span class="sxs-lookup"><span data-stu-id="f79d2-105">Returns an integer representing the Z bits of an array of Pauli operators.</span></span>

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="f79d2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="f79d2-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="f79d2-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="f79d2-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="f79d2-108">Bir tamsayı olarak temsil edilecek Pauli işleçleri dizisi.</span><span class="sxs-lookup"><span data-stu-id="f79d2-108">An array of Pauli operators to be represented as an integer.</span></span>



## <a name="output--int"></a><span data-ttu-id="f79d2-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f79d2-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f79d2-110">İkili temsili $ (p_ {62} \, P_ {61} \, \noktalar p_0) $ olan bir tamsayı $x $ \, , burada $p _i = $0, veya ise $p `paulis[i]` `PauliI` `PauliX` = $1 ' dir `paulis[i]` `PauliY` `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="f79d2-110">An integer $x$ with binary representation $(p_{62}\,p_{61}\,\dots\,p_0)$, where $p_i = 0$ if `paulis[i]` is `PauliI` or `PauliX` and where $p_i = 1$ if `paulis[i]` is `PauliY` or `PauliZ`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f79d2-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="f79d2-111">Remarks</span></span>

<span data-ttu-id="f79d2-112">Dizi uzunluğu 63 ' den büyükse işlev oluşturulur `paulis` .</span><span class="sxs-lookup"><span data-stu-id="f79d2-112">The function will throw if the length of `paulis` array is greater than 63.</span></span>

## <a name="see-also"></a><span data-ttu-id="f79d2-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f79d2-113">See Also</span></span>

- [<span data-ttu-id="f79d2-114">Microsoft. hisse. bit düzeyinde. Xbit</span><span class="sxs-lookup"><span data-stu-id="f79d2-114">Microsoft.Quantum.Bitwise.XBits</span></span>](xref:Microsoft.Quantum.Bitwise.XBits)