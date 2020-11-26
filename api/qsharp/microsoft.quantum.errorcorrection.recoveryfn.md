---
uid: Microsoft.Quantum.ErrorCorrection.RecoveryFn
title: RecoveryFn Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoveryFn
qsharp.summary: Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.
ms.openlocfilehash: ac3c17da172a8f906643091745e9278bb17d02eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200518"
---
# <a name="recoveryfn-user-defined-type"></a><span data-ttu-id="465d3-102">RecoveryFn Kullanıcı tanımlı tür</span><span class="sxs-lookup"><span data-stu-id="465d3-102">RecoveryFn user defined type</span></span>

<span data-ttu-id="465d3-103">Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="465d3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="465d3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="465d3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="465d3-105">Bir hata syndrobeni, algılanan hatayı düzeltecek bir dizi işlem ile eşleyen işlev için yazın `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="465d3-105">Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.</span></span>

```qsharp

newtype RecoveryFn = ((Microsoft.Quantum.ErrorCorrection.Syndrome -> Pauli[]));
```

