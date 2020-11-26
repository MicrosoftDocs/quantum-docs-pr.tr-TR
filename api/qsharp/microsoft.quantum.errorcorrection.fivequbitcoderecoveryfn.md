---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 47e8a74d3631be2209537679ec9786a8dab63c58
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200790"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="44082-102">FiveQubitCodeRecoveryFn işlevi</span><span class="sxs-lookup"><span data-stu-id="44082-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="44082-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="44082-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="44082-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="44082-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="44082-105">Hata sendromu ölçümlerini, ⟦ 5, 1, 3 ⟧ hisse kodu için tablo aramasına göre düzeltme ile ilgili hata ile eşleyen bir işlev döndürür.</span><span class="sxs-lookup"><span data-stu-id="44082-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="44082-106">Çıkış: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="44082-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="44082-107">`RecoveryFn`Bir sendromu ölçümü alan `Result[]` ve `Pauli[]` algılanan hatayı düzelten işleçleri döndüren tür işlevi.</span><span class="sxs-lookup"><span data-stu-id="44082-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="44082-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="44082-108">Remarks</span></span>

<span data-ttu-id="44082-109">$1 $ ağırlığının tüm hatalarını tekrarlayarak, toplam $3 \ kez 5 = 15 $ olası, önemsiz olmayan Syndromes elde ediyoruz.</span><span class="sxs-lookup"><span data-stu-id="44082-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="44082-110">Kimlik ile birlikte bir hata tablosu ve ilgili sendromu oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="44082-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="44082-111">Bu tablonun verdiği 5 qubit kodu için: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ $Y _i $ ile $X _i $ ve $Z _i $ Syndromes ' i ekleyerek elde edilir.</span><span class="sxs-lookup"><span data-stu-id="44082-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="44082-112">Tablo arama kurtarmasında yer alan sıralamanın, bitvektörleri tamsayılara (little endian kullanarak) dönüştürerek verildiğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="44082-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="44082-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="44082-113">See Also</span></span>

- [<span data-ttu-id="44082-114">Microsoft. hisse. Errordüzeltmesini. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="44082-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)