---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: ca22b090f2b2613f07caef698941ea608374ab1e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203323"
---
# <a name="applytransposition-operation"></a>ApplyTransposition işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bu işlem, dizin üzerindeki genonu, `a` `b` belirtilen eyalet- `register` $n $ uzunluğundaki vektörde bulunan dizindeki genlerle değiştirir.  `a`Eşitse `b` , eyalet vektörü değiştirilmez.

## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)

İlk dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

İkinci dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Transkonumun uygulandığı $n $ qubits listesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

