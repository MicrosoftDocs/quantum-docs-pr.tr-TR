---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: Applypauömrü Rombitstring işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: e0edd8420127339116e525421ba23e246dcf0a45
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841584"
---
# <a name="applypaulifrombitstring-operation"></a>Applypauömrü Rombitstring işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir Boolean dizisinin karşılık gelen biti verilen bir girişle eşleşiyorsa, dizideki her bir qubit üzerinde Pauli işleci uygular.

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Nereye uygulanacak Pauli işleci `qubits[idx]``bitsApply == bits[idx]`


### <a name="bitapply--bool"></a>bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)

bit Bu değer ise Pauli Uygula


### <a name="bits--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]

İçinde hangi karşılık gelen qubitin çalışılmalıdır belirten Boole kaydı `qubits`


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Belirtilen Pauli işlecinin seçmeli olarak uygulanacağı hisse kayıt



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Boole dizisi ve hisse kayıt uzunluğu eşit olmalıdır.