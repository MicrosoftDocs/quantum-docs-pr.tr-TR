---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Assertqubitişsınstatewithıntoleransınıntoleransı işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 1ceb7243cba93e42c67cc3655283a5d07c96863e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202218"
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