---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854300"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState işlevi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir karma durumun bir listesini hazırlayan bir işlem döndürür.
"Yukarıda açıklanan karışık durum", | ψ ⟩ = Σi √ Pi | i ⟩ | garbagei ⟩ 'in {PI} katsayısının bir vektörü tarafından belirtilen durumlarını ifade eder. Bu formun durumları, karışık durumlara azaltılabilir ρ ≔ Pi | ı ⟩ ⟨ ı | "çöp" kaydının (yani, hesaplama temelinde köşegen bir durum) üzerinde izleme yaparak.

https://arxiv.org/pdf/1805.03662.pdf?page=15Daha fazla tartışma için bkz..

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Description

, Söz konusu gösterimi bir durum hazırlama işlemi olarak döndüren belirli bir yoğunluk matrisini temsil etmek için hisse ROM tekniğini kullanır.

Özellikle, $N $ katsayıları $ \ alpha_j $ olan bir liste verildiğinde bu işlev bir yaklaşık $ $ \begin{hizalaması} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} hazırlamak için hisse \end{hizalaması} $ $ karma durumun $ $ \begin{hizalaması} \rho = \ sum_ {j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{hizalaması} $ $ her $p _j $, verilen katsayı $ \ alpha_j $ olan $ $ \begin{hizalaması} \left | şeklinde bir yaklaşık değer. p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} Her $j $ için \le \frac{\epsilon}{N} \end{hizalaması} $ $.

Başlangıçta $ \tus\ket{00\cnoktalar 0} durumunda bir dizin kaydı ve çöp qubits kaydı geçirildiğinde, {0} döndürülen işlem her iki kaydı da $ \tilde \rho $ ' ın ize hazırlar $ $ \begin{hizalaması} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{hizalaması} $ $, çöp yazmacı sıfırlama ve ayırmayı kaldırma, hedef hatası $ \epsilon $ içinde için istenen hazırlığı yapar.

## <a name="input"></a>Giriş

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Hedef hata $ \ Epsilon $.


### <a name="coefficients--double"></a>katsayılar: [Double](xref:microsoft.quantum.lang-ref.double)[]

Taban durumlarının olasılığını belirten $N $ katsayıları dizisi.
Negatif sayılar $-\ alpha_j $ pozitif $ | \ alpha_j | $ olarak kabul edilir.



## <a name="output--mixedstatepreparation"></a>Çıkış: [Mixedstatehazırlama](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Birleşik bir dizin ve çöp kaydı üzerine bir birleşme olarak $ \tilde \rho $ hazırlayan bir işlem.

## <a name="example"></a>Örnek

Aşağıdaki kod parçacığı $3 $-qubit durumu $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} için bir yol hazırlar {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, burada $ \vec\alpha = (1.0, 2,0, 3,0, 4,0, 5,0) $ ve hedef hata, $10 ^ {-3} $:

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a>Açıklamalar

Bu işleme sunulan katsayılar, 1-norm sonrasında normalleştirilirler, bu nedenle katsayıların her zaman geçerli bir kategorik olasılık dağılımı tanımlayacak şekilde kabul edilir.

## <a name="references"></a>Başvurular

- Doğrusal T karmaşıklığı olan elektronik Spectra 'yi, doğrusal T karmaşıklığı, Craig Bebush, Craig Gidney, Dominic W. Braz, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut Neven ile kodlama https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. hazırlık. PurifiedMixedStateWithData](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)