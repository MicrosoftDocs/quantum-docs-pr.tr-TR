---
uid: Microsoft.Quantum.Canon.CControlled
title: Cdenetlenen işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: 76e663e9a4b53c7ed74a1b70da516fb07958923b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216906"
---
# <a name="ccontrolled-function"></a>Cdenetlenen işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlem işlemi verildiğinde, bir klasik denetim biti doğru ise op 'yi uygulayan yeni bir işlem döndürür. Yoksa `false` , hiçbir şey olmaz.

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>Giriş

### <a name="op--t--unit"></a>Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Koşullu olarak uygulanacak bir işlem.



## <a name="output--boolt--unit"></a>Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) 

Klasik denetim biti doğru ise op olan yeni bir işlem.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Koşullu olarak uygulanacak işlemin giriş türü.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. CControlledC](xref:Microsoft.Quantum.Canon.CControlledC)
- [Microsoft. hisse. Canon. Ccontroltada](xref:Microsoft.Quantum.Canon.CControlledA)
- [Microsoft. hisse. Canon. CControlledCA](xref:Microsoft.Quantum.Canon.CControlledCA)