---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: _DeltaParityCNOTbitstring işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726420"
---
# <a name="_deltaparitycnotbitstring-function"></a>_DeltaParityCNOTbitstring işlevi

Ad alanı: [Microsoft. hisse. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Leyebilir [](https://nuget.org/packages/)


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