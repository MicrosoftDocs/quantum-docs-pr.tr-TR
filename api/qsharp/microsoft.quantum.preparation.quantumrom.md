---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Miktar Tumrom işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229894"
---
# <a name="quantumrom-function"></a>Miktar Tumrom işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Miktarı kullanım dışı bırakıldı. Lütfen <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> bunun yerine kullanın.

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



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a>Çıkış: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL)

## <a name="first-parameter"></a>İlk parametre

`(x,(y,z))` `x = y + z` Ayrılan toplam qubit sayısı, `y` yazmaç için qubit sayısı `LittleEndian` ve `z` çöp qubit sayısı olan bir kayıt düzeni.

## <a name="second-parameter"></a>İkinci parametre

Katsayı dizisinin tek norm $ \ sum_j | \ alpha_j | $.

## <a name="third-parameter"></a>Üçüncü parametre

Unitary $U $.

## <a name="references"></a>Başvurular

- Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662