---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851772"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys işlevi

Ad alanı: [Microsoft. hisse. Chemistry](xref:Microsoft.Quantum.Chemistry)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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