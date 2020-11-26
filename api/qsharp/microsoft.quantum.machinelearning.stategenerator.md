---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: 5c9643f5c917ff3cb25fa8c046856b03cc287edd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211568"
---
# <a name="stategenerator-user-defined-type"></a>StateGenerator Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Belirli bir girişi sıralı sınıflandırıcıya hazırlayan bir işlem açıklar.

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="nqubits--int"></a>NQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Kodlanan girişin tanımlandığı qubit sayısı.
### <a name="prepare--littleendian--unit--is-adj--ctl"></a>Prepare: [litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit)  , sıfatı + CTL

Bir qubits 'in küçük endian kaydındaki kodlanmış girişi hazırlayan bir işlem `NQubits` .