---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728136"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx işlevi

Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)

Leyebilir [](https://nuget.org/packages/)


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