---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Assertqubitişsınstatewithıntoleransınıntoleransı işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: b40c5c4f731190c8c0d00d33718680e5448bf767
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829795"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>Assertqubitişsınstatewithıntoleransınıntoleransı işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Beklenen durumda bir qubitin olduğunu onaylar.

`expected` karmaşık bir vektörü temsil eder, $ \ket{\psı} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.
$A $, $b $ her birini temsil eden başlıkların ilk öğesi, karmaşık sayının gerçek bölümüdür; ikinci tane ise sanal parçadır.
Son bağımsız değişken, onaylama işlemi yapılan toleransı tanımlar.

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Giriş

### <a name="expected--complexcomplex"></a>beklenen: ([karmaşık](xref:Microsoft.Quantum.Math.Complex),[karmaşık](xref:Microsoft.Quantum.Math.Complex))

Sırasıyla $ \ket {0} $ ve $ \ket $ için karmaşık yükseltilmiş tudes bekleniyordu {1} .


### <a name="register--qubit"></a>kaydolun: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Durumu belirtilmelidir. Bu qubitin diğer ayrılmış qubits 'lerden ayrılabilir olduğunu ve ayrılmadığını unutmayın.


### <a name="tolerance--double"></a>Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)

Gerçek artırlale, beklenmeden sapmasına izin verilen ek tolerans.
Ayrıntılar için aşağıdaki açıklamalara bakın.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

```qsharp
using (qubits = Qubit[2]) {
    // Both qubits are initialized as |0〉: a=(1 + 0*i), b=(0 + 0*i)
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[0], 1e-5);
    AssertQubitIsInStateWithinTolerance((Complex(1., 0.), Complex(0., 0.)), qubits[1], 1e-5);
    Y(qubits[1]);
    // Y |0〉 = i |1〉: a=(0 + 0*i), b=(0 + 1*i)
    AssertQubitIsInStateWithinTolerance((Complex(0., 0.), Complex(0., 1.)), qubits[1], 1e-5);
}
```

## <a name="remarks"></a>Açıklamalar

Aşağıdaki matematiksel matika kodu mi?, MX, My, MZ için ifadeleri doğrulamak için kullanılabilir:

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

Tolerans, \_ $ \langta\psi | \psı\rangle = x 1 I + x 2 x + x 3 Y + x 4 Z $ ve gerçek vektör (Y ₂) tarafından tanımlanan 3 boyutlu gerçek vektör (x ₂, x ₃, x ₄) arasındaki {\infty} $ uzaklığın $L. \_ \_ \_ \_ y ₃, y ₄), ρ = Y ₁ I + y ₂ x + y ₃ Y + y ₄ Z tarafından tanımlanır. burada ρ, kaydın durumuna karşılık gelen yoğunluk matrisi.
Bu yalnızca, tr (ρ) ve tr (| ψ ⟩ ⟨ ψ |) öğelerinin hem 1 hem de (örn. x ₁ = 1/2, y ₁ = 1/2) olduğu varsayımıyla geçerlidir.
Bu durum söz konusu değilse, işlev (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) ve (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) arasındaki l ∞ Distance 'ın tolerans parametresinden daha az olduğunu onaylar.