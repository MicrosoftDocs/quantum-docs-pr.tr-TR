---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225355"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir `BlockEncoding` eşdeğerini bir eşdeğerine dönüştürür `BLockEncodingReflection` .

Diğer bir deyişle, `BlockEncoding` bazı işleci $H $ ' i kodlayan bir Unitary $U $ verildiğinde, onu `BlockEncodingReflection` aynı işleci kodlayan $U ' $ içine dönüştürür, ancak aynı zamanda ' ^ \leger = U ' $ $U de karşılar.
Bu, $U $ öğesinin yardımcı kaydının boyutunu bir qubit artırır.

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Giriş

### <a name="blockencoding--blockencoding"></a>Blockenkodlama: [Blockenkodlama](xref:Microsoft.Quantum.Simulation.BlockEncoding)

`BlockEncoding`Bir yansımaya dönüştürülecek bir Unitary $U $.



## <a name="output--blockencodingreflection"></a>Çıkış: [Blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Bir Unitary $U ' $, Yazmaçları üzerinde ortaklaşa bulunan `a` ve `s` Bu blok-kodlama $H $ $U ve ' ^ \hanger = U ' $ karşılar.

## <a name="remarks"></a>Açıklamalar

Bu, $U $ öğesinin yardımcı kaydının boyutunu bir qubit artırır.

## <a name="references"></a>Başvurular

- Hamiltonian simülasyonu, Qubitiş, Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. simülasyon. Blockenkodlama](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. hisse. simülasyon. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)