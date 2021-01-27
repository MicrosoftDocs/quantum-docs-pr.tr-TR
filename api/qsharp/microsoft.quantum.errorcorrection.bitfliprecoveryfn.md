---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: 1cf2bd944b4dcaadeeca96fa0f576250590962e0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827590"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="8192f-102">BitFlipRecoveryFn işlevi</span><span class="sxs-lookup"><span data-stu-id="8192f-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="8192f-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="8192f-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="8192f-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8192f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8192f-105">⟦ 3, 1, 1 ⟧ bit çevirme kodu için tablo araması tarafından verilen sendromu ölçümü için kurtarma Pauli işlemleri için işlev.</span><span class="sxs-lookup"><span data-stu-id="8192f-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="8192f-106">Çıkış: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="8192f-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="8192f-107">`RecoveryFn`Bir sendromu ölçümü alan `Result[]` ve `Pauli[]` algılanan hatayı düzelten işlemleri döndüren tür işlevi.</span><span class="sxs-lookup"><span data-stu-id="8192f-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="8192f-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8192f-108">See Also</span></span>

- [<span data-ttu-id="8192f-109">Microsoft. hisse. Errordüzeltmesini. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="8192f-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)