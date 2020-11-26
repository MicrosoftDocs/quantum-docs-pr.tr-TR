---
uid: Microsoft.Quantum.Math.InverseModI
title: Evirsemodı işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195384"
---
# <a name="inversemodi-function"></a>Evirsemodı işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi $b $ döndürür.

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)

Ters çevrilen sayı


### <a name="modulus--int"></a>mod: [Int](xref:microsoft.quantum.lang-ref.int)

Sayıların tersine çevrilme olarak mod



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi bir tamsayı $b $.