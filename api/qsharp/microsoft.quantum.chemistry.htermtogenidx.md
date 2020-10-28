---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728129"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx işlevi

Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)

Leyebilir [](https://nuget.org/packages/)


Veri biçimindeki Hamiltonian terimini `HTerm` bir Generatorındex öğesine dönüştürür.

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Giriş

### <a name="term--hterm"></a>terim: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)

Verileri biçimde girin `HTerm` .


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)[]

Generatorındex 'e ek bilgiler eklendi.



## <a name="output--generatorindex"></a>Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Tarafından temsil edilen bir Hamiltonian terimini `term` , tarafından eklenen ek bilgilerle birlikte temsil eden bir Generatorındex `termType` .