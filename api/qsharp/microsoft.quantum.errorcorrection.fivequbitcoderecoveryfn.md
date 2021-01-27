---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853121"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn işlevi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hata sendromu ölçümlerini, ⟦ 5, 1, 3 ⟧ hisse kodu için tablo aramasına göre düzeltme ile ilgili hata ile eşleyen bir işlev döndürür.

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Çıkış: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`Bir sendromu ölçümü alan `Result[]` ve `Pauli[]` algılanan hatayı düzelten işleçleri döndüren tür işlevi.

## <a name="remarks"></a>Açıklamalar

$1 $ ağırlığının tüm hatalarını tekrarlayarak, toplam $3 \ kez 5 = 15 $ olası, önemsiz olmayan Syndromes elde ediyoruz.
Kimlik ile birlikte bir hata tablosu ve ilgili sendromu oluşturulur. Bu tablonun verdiği 5 qubit kodu için: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ $Y _i $ ile $X _i $ ve $Z _i $ Syndromes ' i ekleyerek elde edilir. Tablo arama kurtarmasında yer alan sıralamanın, bitvektörleri tamsayılara (little endian kullanarak) dönüştürerek verildiğini unutmayın.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)