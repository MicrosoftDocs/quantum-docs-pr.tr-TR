---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852346"
---
# <a name="operationpowc-function"></a>OperationPowC işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir güce yükseltir.
Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.

Diğer bir deyişle, $U $ geçidini temsil eden bir işlem verildiğinde, bir Power $m $ için ^ d $ $U yeni bir işlem döndürür.

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>Giriş

### <a name="op--t--unit--is-ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

Tekrarlanması için kullanılacak ağ geçidini temsil eden bir işlem $U.


### <a name="power--int"></a>güç: [Int](xref:microsoft.quantum.lang-ref.int)

$U $ öğesinin tekrarlanması için kaç kez yineleneceğini.



## <a name="output--t--unit--is-ctl"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  CTL

$U ^ d $ temsil eden yeni bir işlem; burada $m = \texttt{Power} $.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Kapatılacak işlemin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)