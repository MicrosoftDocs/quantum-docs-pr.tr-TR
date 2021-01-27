---
uid: Microsoft.Quantum.Convert.BoolArrayAsPauli
title: BoolArrayAsPauli işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsPauli
qsharp.summary: Given a bit string, returns a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.
ms.openlocfilehash: c11ca05ad8a939d704547c65a8e8a6537d0df4b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834242"
---
# <a name="boolarrayaspauli-function"></a>BoolArrayAsPauli işlevi

Ad alanı: [Microsoft. hisse. Convert](xref:Microsoft.Quantum.Convert)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir bit dizesi verildiğinde, tek qubit Pauli işleçleri dizisi olarak temsil edilen bir multi-qubit Pauli işleci döndürür.

```qsharp
function BoolArrayAsPauli (pauli : Pauli, bitApply : Bool, bits : Bool[]) : Pauli[]
```


## <a name="input"></a>Giriş

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Burada qubits 'e uygulanacak Pauli işleci `bitsApply == bits[idx]` .


### <a name="bitapply--bool"></a>bitApply: [bool](xref:microsoft.quantum.lang-ref.bool)

bit Bu değer ise Pauli uygulayın.


### <a name="bits--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Boolean dizisi.



## <a name="output--pauli"></a>Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]



## <a name="remarks"></a>Açıklamalar

Boole dizisi ve hisse kayıt uzunluğu eşit olmalıdır.