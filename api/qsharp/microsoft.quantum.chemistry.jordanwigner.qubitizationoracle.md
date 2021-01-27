---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: Qubitişzationoracle işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: cf6fe04b3f629c4ca4a7c27d8519a4cb42d07630
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835845"
---
# <a name="qubitizationoracle-function"></a>Qubitişzationoracle işlevi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Qubitişleştirme işlemini ve çalıştırmak için gereken parametreleri döndürür.

```qsharp
function QubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a>Giriş

### <a name="qsharpdata--jordanwignerencodingdata"></a>Qnetsveri: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

Hamiltonian biçim tarafından açıklanmıştır `JordanWignerEncodingData` .



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a>Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL))

Bir kayıt düzeni: `Int` ayrılan qubit sayısı, `Double` Hamiltonian katsayısının tek norm ve Işlem, Qubitişleştirme tarafından oluşturulan hisse alma işlemidir.