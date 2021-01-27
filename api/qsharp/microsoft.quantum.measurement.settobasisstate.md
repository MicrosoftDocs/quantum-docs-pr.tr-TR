---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854618"
---
# <a name="settobasisstate-operation"></a>SetToBasisState işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Qubit ' i ölçerek ve gerekirse bir bit çevirme uygulayarak belirli bir hesaplama tabanlı duruma bir qubit ayarlar.

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>Giriş

### <a name="desired--__invalidresult__"></a>istenen: __geçersiz <Result>__

Qubitin olarak ayarlanması gereken temel durum.


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Durumu ayarlanacak qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlemin bir sabiti olarak, `M(q)` hemen sonrasında çağırma `SetToBasisState(result, q)` geri döndürülür `result` .