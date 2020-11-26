---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217076"
---
# <a name="arrangedqubits-function"></a>ArrangedQubits işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir dizine göre denetim, hedef ve yardımcı qubits 'i düzenleme

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a>Açıklama

0 dizininde target olan bir qubit dizisi, dizin 2 ^ i 'de ise denetim ı döndürür.  Yardımcı qugeler dizideki diğer tüm konumlara eklenir.

## <a name="input"></a>Giriş

### <a name="controls--qubit"></a>denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)




### <a name="helper--qubit"></a>yardımcı: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--qubit"></a>Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

