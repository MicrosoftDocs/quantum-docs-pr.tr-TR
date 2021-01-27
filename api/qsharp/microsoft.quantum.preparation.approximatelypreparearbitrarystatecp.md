---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP
title: Yaklaşık Telypreparearbitraryıstatecp işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: fbabc320ff153dbceb4453bad95cd5f4c1776583
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856961"
---
# <a name="approximatelypreparearbitrarystatecp-operation"></a>Yaklaşık Telypreparearbitraryıstatecp işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir ölçü kümesi ve az endian kodlu bir hisse kayıt verildiğinde, verilen katsayıların belirli bir kabul toleransına göre tanımlanan bir durumu hazırlar.

```qsharp
operation ApproximatelyPrepareArbitraryStateCP (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Bu işlem, $n $-qubit hesaplama tabanlı durumu $ \ket{0 \cnoktalar 0} $ T_J _j e ^ {i} $ $r karmaşık katlarla rastgele bir hisse ma(Fe{\psi} $ hazırlar.
Özellikle, bu işlemin eylemi bir unitöğeli dönüşüm $U $ tarafından benzetilir ve bu da tüm sıfırları durum üzerinde işlem yapar

$ $ \begin{hizalaması} U\ket {0... 0} & = \ket{\psı} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i T_J} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.
\end{hizalaması} $ $

## <a name="input"></a>Giriş

### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Verilen durum hazırlanırken kullanılacak yaklaşık tolerans.


### <a name="coefficients--complexpolar"></a>katsayılar: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)[]

Mutlak değerleri ve aşama $ (r_j, t_j) ile temsil edilen en fazla $2 ^ n $ karmaşık katsayılar dizisi. $J $ TH katsayısı, küçük endian biçiminde $ \ket{j} $ kodlu durum sayısını dizine ekler.


### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit kodlama numarası durumlarını küçük endian biçiminde kaydeder. Bu durumun, $ \ket{0...0} $ hesaplama tabanlı durumunda başlatılması beklenir.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

_J < $0 $r negatif giriş katsayılarını $ | r_j | $ değeri ile pozitif kabul edilir. `coefficients` $2 ^ n $ değerinden azı belirtilmişse $ (r_j, t_j) = (0,0, 0,0) $ öğeleri ile doldurulur.

## <a name="references"></a>Başvurular

- Senişce Logic devreleri Vivek V. ShENdE, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176