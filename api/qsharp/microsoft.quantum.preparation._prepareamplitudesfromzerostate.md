---
uid: Microsoft.Quantum.Preparation._PrepareAmplitudesFromZeroState
title: _PrepareAmplitudesFromZeroState işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _PrepareAmplitudesFromZeroState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients. Uses state emulation if supported by the target.
ms.openlocfilehash: 94563632d514f66608b14c264a73bdfcc6f50982
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854453"
---
# <a name="_prepareamplitudesfromzerostate-operation"></a>_PrepareAmplitudesFromZeroState işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir ölçü kümesi ve hepsi sıfır durumda olan unentangled qubits 'in küçük endian kodlu hisse kaydına verildiğinde, söz konusu kayıt üzerinde verilen katsayıların açıklandığı bir durum hazırlar. Hedef tarafından destekleniyorsa, durum öykünmesi kullanır.

```qsharp
operation _PrepareAmplitudesFromZeroState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Giriş

### <a name="coefficients--complexpolar"></a>katsayılar: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)[]




### <a name="qubits--littleendian"></a>qubits: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

