---
uid: Microsoft.Quantum.Math.InverseModL
title: Evirsemodl işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 0d768114c84025a067e0b60762e6834fbd36deb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228194"
---
# <a name="inversemodl-function"></a>Evirsemodl işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi $b $ döndürür.

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a>Giriş

### <a name="a--bigint"></a>y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Ters çevrilen sayı


### <a name="modulus--bigint"></a>mod: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Sayıların tersine çevrilme olarak mod



## <a name="output--bigint"></a>Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi bir tamsayı $b $.