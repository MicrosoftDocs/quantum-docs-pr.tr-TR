---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: Yaklaşık Telnalexz işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 5e254c2b2d6cbf29b428f4d55aef0e61356e3480
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217110"
---
# <a name="approximatelymultiplexz-operation"></a>Yaklaşık Telnalexz işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubit dizisine bağlı bir Pauli Z dönüşü, belirli bir toleranstan göre küçük döndürme açılarını kesiluygular.

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bu, $n $-qubit numarası State $ \ket{j} $ tarafından denetlendiğinde $ \ theta_j $ hakkında tek-qubit Pauli işleci $Z $ ile birlikte döndürmeler gerçekleştiren çarpma kontrollü Unitary işlemini uygular.
Özellikle, bu işlem Unitary tarafından temsil edilebilir

$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}.
\end{hizalaması} $ $

## <a name="input"></a>Giriş

### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Küçük katsayıların kesilme toleransı.


### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

Dizi $2 ^ n $ katsayısı $ \ theta_j $. $J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.


### <a name="control--littleendian"></a>Denetim: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

$E ^ {i P \ theta_j} $ tarafından döndürülen tek qubit kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.

## <a name="references"></a>Başvurular

- Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. MultiplexZ](xref:Microsoft.Quantum.Canon.MultiplexZ)