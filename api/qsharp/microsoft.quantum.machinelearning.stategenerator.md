---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732303"
---
# <a name="stategenerator-user-defined-type"></a>StateGenerator Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Belirli bir girişi sıralı sınıflandırıcıya hazırlayan bir işlem açıklar.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="nqubits--int"></a>NQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Kodlanan girişin tanımlandığı qubit sayısı.
### <a name="prepare--littleendian--unit-adj--ctl"></a>Hazırla: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) ayarlama + CTL

Bir qubits 'in küçük endian kaydındaki kodlanmış girişi hazırlayan bir işlem `NQubits` .