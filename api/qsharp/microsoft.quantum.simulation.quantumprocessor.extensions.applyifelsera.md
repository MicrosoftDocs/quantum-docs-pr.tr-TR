---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: ApplyIfElseRA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: bcc52c6e2b4dfc6354e12c57e19739ac021d2e8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734026"
---
# <a name="applyifelsera-operation"></a>ApplyIfElseRA işlemi

Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Leyebilir [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit
```


## <a name="input"></a>Giriş

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __geçersiz <Result>__




### <a name="onresultzeroop--t--unit-adj"></a>Onresultsıfırlaması op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması




### <a name="zeroarg--t"></a>Sıfırlama bağımsız değişkeni: 'T




### <a name="onresultoneop--u--unit-adj"></a>onResultOneOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması




### <a name="onearg--u"></a>oneArg: ' U





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U

