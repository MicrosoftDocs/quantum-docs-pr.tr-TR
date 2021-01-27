---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: Yaklaşık Telnalexpauli işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 1fc8a8857b6b37d4c3e812a3c4cb2941b9238800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844584"
---
# <a name="approximatelymultiplexpauli-operation"></a>Yaklaşık Telnalexpauli işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubit dizisine bağlı bir Pauli dönüşü uygular, belirli bir toleransa göre küçük döndürme açılarını kesiliyor.

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bu, $n $-qubit numarası State $ \ket{j} $ tarafından denetlendiğinde $ \ theta_j $ hakkında tek-qubit Pauli işleci $P $ ile birlikte döndürmeler gerçekleştiren bir çarpma kontrollü Unitary işlemi uygular.
Özellikle, bu işlemin eylemi Unitary tarafından temsil edilir

$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}.
\end{hizalaması}

##

## <a name="input"></a>Giriş

### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Küçük katsayıların kesilme toleransı.


### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

Dizi $2 ^ n $ katsayısı $ \ theta_j $. $J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.


### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli işleci $P $, döndürme eksenini belirler.


### <a name="control--littleendian"></a>Denetim: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

$E ^ {i P \ theta_j} $ tarafından döndürülen tek qubit kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)