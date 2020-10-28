---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: b6f7e7d6d51e531b0ec9e7e4f2f5772038421933
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726282"
---
# <a name="applyconditionallya-operation"></a>ApplyConditionallyA işlemi

Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Leyebilir [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Giriş

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __geçersiz <Result>__ []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues değerleri __: <Result> geçersiz__ []




### <a name="onequalop--t--unit-adj"></a>onEqualOp: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması




### <a name="equalarg--t"></a>equalArg: 'T




### <a name="onnonequalop--u--unit-adj"></a>onNonEqualOp: ' U => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U

