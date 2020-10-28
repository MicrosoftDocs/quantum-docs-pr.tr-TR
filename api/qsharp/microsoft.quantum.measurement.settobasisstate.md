---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733602"
---
# <a name="settobasisstate-operation"></a>SetToBasisState işlemi

Ad alanı: [Microsoft. hisse. ölçümü](xref:Microsoft.Quantum.Measurement)

Leyebilir [](https://nuget.org/packages/)


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