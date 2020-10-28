---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726935"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery işlevi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Leyebilir [](https://nuget.org/packages/)


Belirli bir qubits kaydındaki belirli bir Pauli işlemleri tablosu için, bu işlev bir `RecoveryFn` tablo arama kod çözme işlemini, verilen Pauli işlemleri dizisiyle ilgili olarak gereken tüm bilgileri içeren türünde bir nesne döndürür.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Giriş

### <a name="table--pauli"></a>Tablo: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Belirli bir qubit kayıt üzerinde çalışan Pauli işlemleri tablosu



## <a name="output--recoveryfn"></a>Çıkış: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

`RecoveryFn`Belirli bir sendromu dizisiyle ilişkili bir eşleme olan bir eşlem olan türü, yani, `Syndrome -> Pauli[]` karşılık gelen bir Pauli düzeltme işlemi.