---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216022"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx işlevi

Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Bir dizini, veri biçimindeki Hamiltonian terimine `HTerm[]` bir Generatorındex olarak dönüştürür.

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Giriş

### <a name="data--hterm"></a>veri: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Verileri biçimde girin `HTerm[]` .


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)[]

Generatorındex 'e ek bilgiler eklendi.


### <a name="idx--int"></a>idx: [Int](xref:microsoft.quantum.lang-ref.int)

Hamiltonian 'nin bir teriminin dizini



## <a name="output--generatorindex"></a>Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Tarafından temsil edilen bir Hamiltonian terimini `data[idx]` , tarafından eklenen ek bilgilerle birlikte temsil eden bir Generatorındex `termType` .