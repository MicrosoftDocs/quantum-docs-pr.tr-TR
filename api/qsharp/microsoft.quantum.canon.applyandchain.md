---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: Applyandzinciri işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: 3991ded1a9c70bf4b58d19b0304a1df3b31896d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842012"
---
# <a name="applyandchain-operation"></a>Applyandzinciri işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


VE kapıları zincirini hesaplar

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a>Description

Geçici sonuçları hesaplamak için yardımcı qubits açıkça belirtilmelidir.
Bu kaydın uzunluğu `Length(ctrlRegister) - 2` , en az iki denetim varsa, aksi takdirde Uzunluk 0 ' dır.

## <a name="input"></a>Giriş

### <a name="auxregister--qubit"></a>yedek kayıt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="ctrlregister--qubit"></a>ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

