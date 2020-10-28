---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728130"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys işlevi

Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)

Leyebilir [](https://nuget.org/packages/)


Veri biçimindeki Hamiltonian `HTerm[]` bir GeneratorSystem öğesine dönüştürür.

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Giriş

### <a name="data--hterm"></a>veri: [Hterm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Verileri biçimde girin `HTerm[]` .


### <a name="termtype--int"></a>termType: [Int](xref:microsoft.quantum.lang-ref.int)[]

Generatorındex 'e ek bilgiler eklendi.



## <a name="output--generatorsystem"></a>Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Girişin gösterdiği Hamiltonian 'yi temsil eden bir GeneratorSystem `data` .