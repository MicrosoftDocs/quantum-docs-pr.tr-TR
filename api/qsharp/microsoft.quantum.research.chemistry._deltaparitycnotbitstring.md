---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 0c0da60e3c389f8208f9f7d5c84a09893f3c1bda
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226086"
---
# <a name="_deltaparitycnotbitstring-function"></a>_DeltaParityCNOTbitstring işlevi

Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Paket: [Microsoft. hisse. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Klasik işleme adımı `ApplyDeltaParity` .
Bu, herhangi iki PQRS arasındaki eşlik farkını değerlendirmek için denetim qubits listesini hesaplar... Hatta uzunluk terimi.

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>Giriş

### <a name="prevfermionicterm--int"></a>Prevfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>Nextfermıonicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>Çıkış: ([Int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])



## <a name="remarks"></a>Açıklamalar

Bu, koşulların uzunluğunun eşit olduğunu varsayar.
İki terim arasındaki eşlik farkı için denetim listesini hesaplar.
Bu, giriş listelerinin artan düzende sıralanacağını varsayar.