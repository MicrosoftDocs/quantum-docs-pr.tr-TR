---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: e4136add99ab7fb6904d7cac3c7f3e5076cc3176
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213676"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="a6f78-102">TableLookupRecovery işlevi</span><span class="sxs-lookup"><span data-stu-id="a6f78-102">TableLookupRecovery function</span></span>

<span data-ttu-id="a6f78-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="a6f78-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="a6f78-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6f78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a6f78-105">Belirli bir qubits kaydındaki belirli bir Pauli işlemleri tablosu için, bu işlev bir `RecoveryFn` tablo arama kod çözme işlemini, verilen Pauli işlemleri dizisiyle ilgili olarak gereken tüm bilgileri içeren türünde bir nesne döndürür.</span><span class="sxs-lookup"><span data-stu-id="a6f78-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="a6f78-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a6f78-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="a6f78-107">Tablo: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="a6f78-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="a6f78-108">Belirli bir qubit kayıt üzerinde çalışan Pauli işlemleri tablosu</span><span class="sxs-lookup"><span data-stu-id="a6f78-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="a6f78-109">Çıkış: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="a6f78-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="a6f78-110">`RecoveryFn`Belirli bir sendromu dizisiyle ilişkili bir eşleme olan bir eşlem olan türü, yani, `Syndrome -> Pauli[]` karşılık gelen bir Pauli düzeltme işlemi.</span><span class="sxs-lookup"><span data-stu-id="a6f78-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>