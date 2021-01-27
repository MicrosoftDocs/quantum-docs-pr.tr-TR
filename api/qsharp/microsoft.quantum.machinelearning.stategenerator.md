---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854885"
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