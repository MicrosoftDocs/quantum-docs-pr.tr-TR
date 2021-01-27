---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: ApplyConditionallyIntrinsicCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 137168d7360842df18d1ed2893f7a1b2e9a548cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854212"
---
# <a name="applyconditionallyintrinsicca-operation"></a>ApplyConditionallyIntrinsicCA işlemi

Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __geçersiz <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues değerleri __: <Result> geçersiz__[]




### <a name="onequalop--unit--unit--is-adj--ctl"></a>onequalop: [birim](xref:microsoft.quantum.lang-ref.unit) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL




### <a name="onnonequalop--unit--unit--is-adj--ctl"></a>onnonequalop: [birim](xref:microsoft.quantum.lang-ref.unit) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

