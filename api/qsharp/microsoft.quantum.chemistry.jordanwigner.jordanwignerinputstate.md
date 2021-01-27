---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 18adf28b4e99c825f14e9271791ded069e687901
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837686"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>JordanWignerInputState Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


İlk durumun hazırlanmasını göstermek için C# ' den Q # ' a geçirilen verilerin biçimi, temsil edilen verilerin anlamı onu alan algoritma tarafından belirlenir.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

