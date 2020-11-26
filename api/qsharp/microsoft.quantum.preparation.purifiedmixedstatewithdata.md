---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229962"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir veri toplamayı temsil eden bir yazmaç ile, belirli bir karma durumun bir listesini hazırlayan bir işlem döndürür.
"Verilerle birlikte açıklanan karma durum", Σi √ Pi | i ⟩ | Xi ⟩ | garbagei ⟩ biçiminde ifade eder; burada her Xi, YAZMAÇ | i ⟩ ile ilişkili ek verileri bir bit dizesidir.

https://arxiv.org/pdf/1805.03662.pdf?page=15Daha fazla tartışma için bkz..

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Açıklama

, Söz konusu gösterimi bir durum hazırlama işlemi olarak döndüren belirli bir yoğunluk matrisini temsil etmek için hisse ROM tekniğini kullanır.

Özellikle, $N $ katsayıları $ \ alpha_j $ olan bir liste verildiğinde ve her bir katsayı ile ilişkili bitstring $ \ VEC{x}_j $, bu işlev bir yaklaşık değer hazırlamak Için hisse $ $ \begin{hizalaması} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{hizalaması} $ $ karma durumun $ $ \begin{hizalaması} \rho = \sum_{j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{hizalaması} $ $ burada her $p _j $, $ $ \begin{hizalaması} \left gibi verilen katsayı $ \ alpha_j $ ' i n p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} Her $j $ için \le \frac{\epsilon}{N} \end{hizalaması} $ $.

Başlangıçta $ \tus\ket{00\cnoktalar 0} durumunda bir dizin kaydı ve çöp qubits kaydı geçirildiğinde, {0} döndürülen işlem her iki kaydı da $ \tilde \rho $ ' ın ize hazırlar $ $ \begin{hizalaması} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\Text{Garbage} _j}, \end{hizalaması} $ $, çöp yazmacı sıfırlama ve ayırmayı kaldırma, hedef hatası $ \epsilon $ içinde için istenen hazırlığı yapar.

## <a name="input"></a>Giriş

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Hedef hata $ \ Epsilon $.


### <a name="coefficients--doublebool"></a>katsayılar: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []

Taban durumlarının olasılığını belirten $N $ katsayıları dizisi, her bir katla ilişkili $ \vec{x} _j $ ile birlikte.
Negatif sayılar $-\ alpha_j $ pozitif $ | \ alpha_j | $ olarak kabul edilir.



## <a name="output--mixedstatepreparation"></a>Çıkış: [Mixedstatehazırlama](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Birleşik bir dizin ve çöp kaydı üzerine bir birleşme olarak $ \tilde \rho $ hazırlayan bir işlem.

## <a name="remarks"></a>Açıklamalar

Bu işleme sunulan katsayılar, 1-norm sonrasında normalleştirilirler, bu nedenle katsayıların her zaman geçerli bir kategorik olasılık dağılımı tanımlayacak şekilde kabul edilir.

## <a name="references"></a>Başvurular

- Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. hazırlık. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)