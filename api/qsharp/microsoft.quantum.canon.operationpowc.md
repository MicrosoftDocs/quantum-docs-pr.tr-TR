---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728495"
---
# <a name="operationpowc-function"></a>OperationPowC işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Bir işlemi bir güce yükseltir.
Değiştirici, `C` işlemin denetlenebilir olduğunu gösterir.

Diğer bir deyişle, $U $ geçidini temsil eden bir işlem verildiğinde, bir Power $m $ için ^ d $ $U yeni bir işlem döndürür.

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>Giriş

### <a name="op--t--unit-ctl"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL

Tekrarlanması için kullanılacak ağ geçidini temsil eden bir işlem $U.


### <a name="power--int"></a>güç: [Int](xref:microsoft.quantum.lang-ref.int)

$U $ öğesinin tekrarlanması için kaç kez yineleneceğini.



## <a name="output--t--unit-ctl"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) CTL

$U ^ d $ temsil eden yeni bir işlem; burada $m = \texttt{Power} $.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Kapatılacak işlemin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)