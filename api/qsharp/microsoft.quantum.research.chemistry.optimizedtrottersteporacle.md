---
uid: Microsoft.Quantum.Research.Chemistry.OptimizedTrotterStepOracle
title: Optimizedtroırsteporacle işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: OptimizedTrotterStepOracle
qsharp.summary: Returns optimized Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: 523a31564ae5f054fd60161f9981c43d3467f3d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842282"
---
# <a name="optimizedtrottersteporacle-function"></a>Optimizedtroırsteporacle işlevi

Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


En iyileştirilmiş araba adımı işlemini ve çalıştırmak için gereken parametreleri döndürür.

```qsharp
function OptimizedTrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Giriş

### <a name="qsharpdata--jordanwignerencodingdata"></a>Qnetsveri: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian biçim tarafından açıklanmıştır `JordanWignerEncodingData` .


### <a name="trotterstepsize--double"></a>Troesstepsize: [çift](xref:microsoft.quantum.lang-ref.double)

Rahatlık tümleştirici için adım boyutu.


### <a name="trotterorder--int"></a>Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)

Araba tümleştirici sırası.



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL))

Bir demet:, `Int` ayrılan qubit sayısı,, `Double` `1.0/trotterStepSize` , ve işlem, sorun.