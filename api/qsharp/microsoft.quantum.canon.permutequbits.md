---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Permütasyon Tequbits işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852336"
---
# <a name="permutequbits-operation"></a>Permütasyon Tequbits işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


DEĞIŞTIRME işlemini kullanarak permütasyon qutes.

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="ordering--int"></a>sıralama: [Int](xref:microsoft.quantum.lang-ref.int)[]

Qubits 'in, bu dizindeki qubit 'in Şu anda [i] sıralamada olacağı yeni sıralamasını açıklar.


### <a name="register--qubit"></a>kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Üzerinde işlem yapmak için qubit kaydolun.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

Verilen sıralama = [2, 1, 0] ve Register $ \ket{\ alpha_0} \ket{\ alpha_1} \ket{\ alpha_2} $, permütasyon Tequbits kaydı $ \ket{\ alpha_2} \ket{\ alpha_1} \ket{\ alpha_0} $ olarak değiştiriyor

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```