---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryStateD
title: Hazırlık Earbitrarna belirtilen işlem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 61f6614821951435828cd28edeb1447cb33f3648
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842367"
---
# <a name="preparearbitrarystated-operation"></a>Hazırlık Earbitrarna belirtilen işlem

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir ölçü kümesi ve az endian kodlu bir hisse kayıt verildiğinde, söz konusu kayıt üzerinde verilen katsayıların açıklandığı bir durum hazırlar.

```qsharp
operation PrepareArbitraryStateD (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bu işlem, $n $-qubit hesaplama tabanlı durumu $ \ket{0 \cnoktalar 0} $ T_J _j e ^ {i} $ $r karmaşık katlarla rastgele bir hisse ma(Fe{\psi} $ hazırlar.
Özellikle, bu işlemin eylemi bir unitöğeli dönüşüm $U $ tarafından benzetimi yapılabilir ve bu durum,

$ $ \begin{hizalaması} U\ket {0... 0} & = \ket{\psı} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i T_J} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{hizalaması} $ $

## <a name="input"></a>Giriş

### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

En fazla $2 ^ n $ gerçek katsayısıdır. $J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit kodlama numarası durumlarını küçük endian biçiminde kaydeder. Bu durumun, $ \ket{0...0} $ hesaplama tabanlı durumunda başlatılması beklenir.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

_J < $0 $r negatif giriş katsayılarını $ | r_j | $ değeri ile pozitif kabul edilir. `coefficients` $2 ^ n $ değerinden azı belirtilmişse $ (r_j, t_j) = (0,0, 0,0) $ öğeleri ile doldurulur.

## <a name="references"></a>Başvurular

- Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. hazırlık. yaklaşık Telypreparearbitrari durumu](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)