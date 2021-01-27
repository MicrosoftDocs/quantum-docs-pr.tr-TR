---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824392"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery işlevi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir qubits kaydındaki belirli bir Pauli işlemleri tablosu için, bu işlev bir `RecoveryFn` tablo arama kod çözme işlemini, verilen Pauli işlemleri dizisiyle ilgili olarak gereken tüm bilgileri içeren türünde bir nesne döndürür.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Giriş

### <a name="table--pauli"></a>Tablo: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Belirli bir qubit kayıt üzerinde çalışan Pauli işlemleri tablosu



## <a name="output--recoveryfn"></a>Çıkış: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`Belirli bir sendromu dizisiyle ilişkili bir eşleme olan bir eşlem olan türü, yani, `Syndrome -> Pauli[]` karşılık gelen bir Pauli düzeltme işlemi.