---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: Çoğullexoperationsfromgenerator işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 59afa9d9a34fe74206118680940d243ed8b2496e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852506"
---
# <a name="multiplexoperationsfromgenerator-operation"></a>Çoğullexoperationsfromgenerator işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


N-qubit numarası State $ \ket{j} $ tarafından denetlenen bir Unitary $V _j $ uygulayan çarpma özellikli Unitary işlemi uygular $U $.

$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 't => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL)

İlk öğenin `Int` $N $ ' nin sayısı ve ikinci öğe ise `(Int -> ('T => () is Adj + Ctl))` $ [0, N-1] $ içinde $j $ bir tamsayı alan ve _j $ $V Unitary işleminin çıkışını çıkaran bir demet.


### <a name="index--littleendian"></a>Dizin: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.


### <a name="target--t"></a>Hedef: 'T

Genel qubit kayıt, $V _j $ üzerinde çalışır.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

`coefficients` $2 ^ n $ değerinden azı belirtilmişse kimlik öğeleriyle doldurulur. Bu uygulama $n-$1 yardımcı qubit kullanır.

## <a name="references"></a>Başvurular

- [*Andrew m. Childs, Dmitrı Maslov, Yunseong Nam, Neil J. No, Yuan su*, arxıv: 1711.10980](https://arxiv.org/abs/1711.10980)