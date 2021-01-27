---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: Hazırlık Yankııteca işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: 6398a875923e03adcb31533dadd881d3c0744840
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856880"
---
# <a name="preparechoistateca-operation"></a>Hazırlık Yankııteca işlemi

Ad alanı: [Microsoft. hisse. hazırlık](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirtilen başvuru ve hedef Yazmaçları üzerinde hem denetimli hem de adjoint türevlerine sahip belirli bir işlem için CHOI – Jamiołkowski durumunu hazırlar.

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="op--qubit--unit--is-adj--ctl"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL




### <a name="reference--qubit"></a>Başvuru: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. hazırlık. hazırlık yankı IState](xref:Microsoft.Quantum.Preparation.PrepareChoiState)