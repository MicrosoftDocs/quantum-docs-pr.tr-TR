---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732146"
---
# <a name="applyblockencodingbylcu-operation"></a>ApplyBlockEncodingByLCU işlemi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Uygulamasının uygulamasıdır `BlockEncodingByLCU` .

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a>Giriş

### <a name="statepreparation--t--unit-adj--ctl"></a>Statehazırlama: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL




### <a name="selector--ts--unit-adj--ctl"></a>seçici: ('T, 'S) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL




### <a name="auxiliary--t"></a>yardımcı: 'T




### <a name="system--s"></a>Sistem: 'S





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="s"></a>Üreticinin

