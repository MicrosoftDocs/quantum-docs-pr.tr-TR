---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: ca9db334bb62e043933f99e405612957831efdcb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733658"
---
# <a name="applyifelser-operation"></a>ApplyIfElseR işlemi

Ad alanı: [Microsoft. hisse. simülasyon. Histumprocessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Leyebilir [](https://nuget.org/packages/)




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a>Giriş

### <a name="measurementresult--__invalidresult__"></a>measurementResult: __geçersiz <Result>__




### <a name="onresultzeroop--t--unit"></a>Onresultsıfırlaması op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) 




### <a name="zeroarg--t"></a>Sıfırlama bağımsız değişkeni: 'T




### <a name="onresultoneop--u--unit"></a>onResultOneOp: ' U => [birimi](xref:microsoft.quantum.lang-ref.unit) 




### <a name="onearg--u"></a>oneArg: ' U





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen


### <a name="u"></a>' U

