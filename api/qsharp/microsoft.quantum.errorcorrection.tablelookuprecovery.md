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
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="7486b-102">TableLookupRecovery işlevi</span><span class="sxs-lookup"><span data-stu-id="7486b-102">TableLookupRecovery function</span></span>

<span data-ttu-id="7486b-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7486b-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7486b-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7486b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7486b-105">Belirli bir qubits kaydındaki belirli bir Pauli işlemleri tablosu için, bu işlev bir `RecoveryFn` tablo arama kod çözme işlemini, verilen Pauli işlemleri dizisiyle ilgili olarak gereken tüm bilgileri içeren türünde bir nesne döndürür.</span><span class="sxs-lookup"><span data-stu-id="7486b-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="7486b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7486b-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="7486b-107">Tablo: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="7486b-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="7486b-108">Belirli bir qubit kayıt üzerinde çalışan Pauli işlemleri tablosu</span><span class="sxs-lookup"><span data-stu-id="7486b-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="7486b-109">Çıkış: [Recoveryfn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="7486b-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="7486b-110">`RecoveryFn`Belirli bir sendromu dizisiyle ilişkili bir eşleme olan bir eşlem olan türü, yani, `Syndrome -> Pauli[]` karşılık gelen bir Pauli düzeltme işlemi.</span><span class="sxs-lookup"><span data-stu-id="7486b-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>