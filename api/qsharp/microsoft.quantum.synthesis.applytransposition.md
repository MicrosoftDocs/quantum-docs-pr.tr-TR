---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: ApplyTransposition işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855575"
---
# <a name="applytransposition-operation"></a>ApplyTransposition işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bu işlem, dizin üzerindeki genonu, `a` `b` belirtilen eyalet- `register` $n $ uzunluğundaki vektörde bulunan dizindeki genlerle değiştirir.  `a`Eşitse `b` , eyalet vektörü değiştirilmez.

## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)

İlk dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

İkinci dizin (0 ile $2 ^ n-$1 arasında bir değer olmalıdır)


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Transkonumun uygulandığı $n $ qubits listesi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

2 qubitlerde $ | 1 \ Rangle $, $ | 2 \ Rangle $ ve $ | 3 \ Rangle $ sayı durumlarıyla ilgili Tekdüzen üst konumunu hazırlayın.

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```