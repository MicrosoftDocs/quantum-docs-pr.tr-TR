---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: Applykoşulsuz işlem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 24d52576d2fb3e83f294874be4b0d1cd6a80f188
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229078"
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

