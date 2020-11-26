---
uid: Microsoft.Quantum.Canon.Bound
title: Bağlantılı işlev
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207607"
---
# <a name="bound-function"></a>Bağlantılı işlev

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tek bir girişte çalışan bir işlem dizisi verildiğinde, belirli bir işlemi sırayla gerçekleştiren yeni bir işlem oluşturur.

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>Giriş

### <a name="operations--t--unit-"></a>işlemler: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []

Belirli bir girişte gerçekleştirilecek işlemler dizisi.



## <a name="output--t--unit"></a>Çıkış: 'T => [birim](xref:microsoft.quantum.lang-ref.unit) 

Belirli bir işlemi girişinde sırayla gerçekleştiren yeni bir işlem.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Dizideki her bir işlemin üzerinde işlem gören hedef.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. hisse. Canon. sını](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft. hisse. Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)