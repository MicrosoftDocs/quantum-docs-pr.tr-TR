---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 9ed0d32c084f183527cac0586ad699417f51df29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852375"
---
# <a name="operationpow-function"></a>OperationPow işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlemi bir güce yükseltir.

Diğer bir deyişle, $U $ geçidini temsil eden bir işlem verildiğinde, bir Power $m $ için ^ d $ $U yeni bir işlem döndürür.

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a>Giriş

### <a name="op--t--unit"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Tekrarlanması için kullanılacak ağ geçidini temsil eden bir işlem $U.


### <a name="power--int"></a>güç: [Int](xref:microsoft.quantum.lang-ref.int)

$U $ öğesinin tekrarlanması için kaç kez yineleneceğini.



## <a name="output--t--unit"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

$U ^ d $ temsil eden yeni bir işlem; burada $m = \texttt{Power} $.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Kapatılacak işlemin türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. OperationPowC](xref:Microsoft.Quantum.Canon.OperationPowC)
- [Microsoft. hisse. Canon. OperationPowA](xref:Microsoft.Quantum.Canon.OperationPowA)
- [Microsoft. hisse. Canon. OperationPowCA](xref:Microsoft.Quantum.Canon.OperationPowCA)