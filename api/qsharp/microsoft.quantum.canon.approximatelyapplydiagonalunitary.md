---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 0a05b8a5891977a08ee2ae6a996657c6a8f3d792
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217127"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a>ApproximatelyApplyDiagonalUnitary işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir qubit yazmacın sayısal temel durumlarına, belirli bir toleranstan göre küçük döndürme açılarını kesilmeye yönelik bir dizi karmaşık aşamalar uygular.

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

Bu işlem, $n $-qubit numarası $ \ket{j} $ üzerinde ^ {i \ theta_j} $ $e karmaşık bir aşama uygulayan diyagonal bir Unitary uygular.
Özellikle, bu işlem Unitary tarafından temsil edilebilir

$ $ \begin{hizalaması} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.
\end{hizalaması} $ $

## <a name="input"></a>Giriş

### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Küçük katsayıların kesilme toleransı.


### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

Dizi $2 ^ n $ katsayısı $ \ theta_j $. $J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

`coefficients` $ \ theta_j = $0,0 öğelerinden daha az $2 ^ n $ belirtilirse, bu öğelerle doldurulur.

## <a name="references"></a>Başvurular

- Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyDiagonalUnitary](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)