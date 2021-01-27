---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847268"
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