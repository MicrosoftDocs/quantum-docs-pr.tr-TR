---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: ApplyIfElseRA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: 11427026d66fc6f46f05004db4dae6f9fa05d921
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855652"
---
# <a name="applyifelsera-operation"></a>ApplyIfElseRA işlemi

Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __geçersiz <Result>__




### <a name="onresultzeroop--t--unit--is-adj"></a>Onresultsıfırlaması op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı




### <a name="zeroarg--t"></a>Sıfırlama bağımsız değişkeni: 'T




### <a name="onresultoneop--u--unit--is-adj"></a>onResultOneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı




### <a name="onearg--u"></a>oneArg: ' U





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U

