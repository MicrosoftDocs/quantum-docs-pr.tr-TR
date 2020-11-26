---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: SteaneCodeRecoveryFns işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 7395996e75c5a1c0c5d13f76d9ec76acae5683c7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200416"
---
# <a name="steanecoderecoveryfns-function"></a><span data-ttu-id="7322a-102">SteaneCodeRecoveryFns işlevi</span><span class="sxs-lookup"><span data-stu-id="7322a-102">SteaneCodeRecoveryFns function</span></span>

<span data-ttu-id="7322a-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7322a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7322a-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7322a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7322a-105">⟦ 7, 1, 3 ⟧ Steane hisse kodu için bir sabitleyici grubunun birleştirilmiş X-ve Z parçaları için kod çözücü.</span><span class="sxs-lookup"><span data-stu-id="7322a-105">Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a><span data-ttu-id="7322a-106">Çıkış: ([Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span><span class="sxs-lookup"><span data-stu-id="7322a-106">Output : ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span></span>

<span data-ttu-id="7322a-107">`RecoveryFn`Bir sendromu ölçümü alan `Result[]` ve `Pauli[]` algılanan hatayı düzelten işlemleri döndüren türdeki işlevlerin listesi.</span><span class="sxs-lookup"><span data-stu-id="7322a-107">Tuple of functions of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="7322a-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7322a-108">See Also</span></span>

- [<span data-ttu-id="7322a-109">Microsoft. hisse. Errordüzeltmesini. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="7322a-109">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="7322a-110">Microsoft. hisse. Errordüzeltmesini. SteaneCodeRecoveryZ</span><span class="sxs-lookup"><span data-stu-id="7322a-110">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)