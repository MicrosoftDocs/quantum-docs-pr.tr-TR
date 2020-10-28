---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Miktar Tumrom işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732623"
---
# <a name="quantumrom-function"></a>Miktar Tumrom işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Leyebilir [](https://nuget.org/packages/)


, Belirli bir yoğunluk matrisini göstermek için hisse ROM tekniğini kullanır.

$N $ katsayısı $ \ alpha_j $ olan bir liste verildiğinde bu işlem, $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} için bir yaklaşık $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ değerini kullanan bir Unitary $U $ döndürür {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $. Bu nedenle, $ \epsilon $ hatası $ | p_j-\frac{| alpha_j |} şeklindedir {\ sum_k | \ alpha_k |} | \le \ Epsilon/N $ ve $ \| \tilde\rho-\rho \| \le \ Epsilon $. Diğer bir deyişle, $ $ \begin{hizalaması} U\ket {0} ^ {\lceil\ Log_2 N\rceıl} \ {0} Tus^ {k} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{Garbage} _j}.
\end{hizalaması} $ $

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>Giriş

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Hedef hata $ \ Epsilon $.


### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

Taban durumlarının olasılığını belirten $N $ katsayıları dizisi.
Negatif sayılar $-\ alpha_j $ pozitif $ | \ alpha_j | $ olarak kabul edilir.



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a>Çıkış: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL)

## <a name="first-parameter"></a>İlk parametre

`(x,(y,z))` `x = y + z` Ayrılan toplam qubit sayısı, `y` yazmaç için qubit sayısı `LittleEndian` ve `z` çöp qubit sayısı olan bir kayıt düzeni.

## <a name="second-parameter"></a>İkinci parametre

Katsayı dizisinin tek norm $ \ sum_j | \ alpha_j | $.

## <a name="third-parameter"></a>Üçüncü parametre

Unitary $U $.

## <a name="references"></a>Referanslar

- Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662