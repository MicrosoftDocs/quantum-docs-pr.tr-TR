---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: Çoğullexoperations işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 267c9c2858090ebe024fd387938e8bd2f8c76867
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728556"
---
# <a name="multiplexoperations-operation"></a>Çoğullexoperations işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir sayı dizisi tarafından denetlenen bir işlem dizisi uygular.

Diğer bir deyişle, $n $-qubit numarası $ \ket{j} $ tarafından denetlenen bir Unitary $V _j $ uygulayan çarpma özellikli Unitary işlemini uygular $U $.

$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a>Giriş

### <a name="unitaries--t--unit-adj--ctl"></a>birimlere ait: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL []

En fazla $2 ^ n $ Unitary işlemi dizisi. $J $ TH işlemi, küçük endian biçiminde bir $ \ket{j} $ kodlu sayı ile dizinlenir.


### <a name="index--littleendian"></a>Dizin: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit denetim kaydı, az endian biçimindeki $ \ket{j} $ sayı durumlarını kodluyor.


### <a name="target--t"></a>Hedef: 'T

Genel qubit kayıt, $V _j $ üzerinde çalışır.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="remarks"></a>Açıklamalar

`coefficients` $2 ^ n $ değerinden azı belirtilmişse kimlik öğeleriyle doldurulur. Bu uygulama $n-$1 yardımcı qubit kullanır.

## <a name="references"></a>Referanslar

- Hisse hızlı bir şekilde tüm hisse simülasyonu 'ne doğru bir şekilde. child. Chil, Dmitrı Maslov, Yunseong Nam, Neil J. No, Yuan su https://arxiv.org/abs/1711.10980