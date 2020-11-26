---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: f8d102cd54222f61058c655e72c63e86d2f5af03
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201215"
---
# <a name="bitfliprecoveryfn-function"></a>BitFlipRecoveryFn işlevi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦ 3, 1, 1 ⟧ bit çevirme kodu için tablo araması tarafından verilen sendromu ölçümü için kurtarma Pauli işlemleri için işlev.

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Çıkış: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`Bir sendromu ölçümü alan `Result[]` ve `Pauli[]` algılanan hatayı düzelten işlemleri döndüren tür işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)