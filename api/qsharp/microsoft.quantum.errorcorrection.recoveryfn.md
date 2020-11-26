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
# <a name="recoveryfn-user-defined-type"></a>RecoveryFn Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir hata syndrobeni, algılanan hatayı düzeltecek bir dizi işlem ile eşleyen işlev için yazın `Pauli[]` .

```qsharp

newtype RecoveryFn = ((Microsoft.Quantum.ErrorCorrection.Syndrome -> Pauli[]));
```

