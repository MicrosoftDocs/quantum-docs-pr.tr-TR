---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841068"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizine göre denetim, hedef ve yardımcı qubits 'i düzenleme

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Description

0 dizininde target olan bir qubit dizisi, dizin 2 ^ i 'de ise denetim ı döndürür.  Yardımcı qugeler dizideki diğer tüm konumlara eklenir.

## <a name="input"></a>Giriş

### <a name="controls--qubit"></a>denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>yardımcı: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

