---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns
title: SteaneCodeRecoveryFns işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryFns
qsharp.summary: Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: b1dd1c2e9a71e58bd8a86d1759a8b6af13a49614
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726972"
---
# <a name="steanecoderecoveryfns-function"></a><span data-ttu-id="f71be-102">SteaneCodeRecoveryFns işlevi</span><span class="sxs-lookup"><span data-stu-id="f71be-102">SteaneCodeRecoveryFns function</span></span>

<span data-ttu-id="f71be-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f71be-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f71be-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f71be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f71be-105">⟦ 7, 1, 3 ⟧ Steane hisse kodu için bir sabitleyici grubunun birleştirilmiş X-ve Z parçaları için kod çözücü.</span><span class="sxs-lookup"><span data-stu-id="f71be-105">Decoder for combined X- and Z-parts of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryFns () : (Microsoft.Quantum.ErrorCorrection.RecoveryFn, Microsoft.Quantum.ErrorCorrection.RecoveryFn)
```


## <a name="output--recoveryfnrecoveryfn"></a><span data-ttu-id="f71be-106">Çıkış: ([Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span><span class="sxs-lookup"><span data-stu-id="f71be-106">Output : ([RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn),[RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn))</span></span>

<span data-ttu-id="f71be-107">`RecoveryFn`Bir sendromu ölçümü alan `Result[]` ve `Pauli[]` algılanan hatayı düzelten işlemleri döndüren türdeki işlevlerin listesi.</span><span class="sxs-lookup"><span data-stu-id="f71be-107">Tuple of functions of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="f71be-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f71be-108">See Also</span></span>

- [<span data-ttu-id="f71be-109">Microsoft. hisse. Errordüzeltmesini. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="f71be-109">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="f71be-110">Microsoft. hisse. Errordüzeltmesini. SteaneCodeRecoveryZ</span><span class="sxs-lookup"><span data-stu-id="f71be-110">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryZ)