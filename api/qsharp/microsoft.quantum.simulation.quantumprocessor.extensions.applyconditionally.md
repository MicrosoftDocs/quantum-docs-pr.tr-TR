---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Applykoşulsuz işlem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 67a4dcba5c193222c06ab429813adf12d7bbedfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847891"
---
# <a name="applyconditionally-operation"></a>Applykoşulsuz işlem

Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Giriş

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __geçersiz <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues değerleri __: <Result> geçersiz__[]




### <a name="onequalop--t--unit"></a>onEqualOp: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) 




### <a name="equalarg--t"></a>equalArg: 'T




### <a name="onnonequalop--u--unit"></a>onNonEqualOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit) 




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U

