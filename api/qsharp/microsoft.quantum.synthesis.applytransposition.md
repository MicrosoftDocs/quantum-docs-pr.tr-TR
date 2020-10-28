---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733938"
---
# <a name="applytransposition-operation"></a>ApplyTransposition işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Leyebilir [](https://nuget.org/packages/)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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

