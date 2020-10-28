---
uid: Microsoft.Quantum.Simulation.GetGeneratorSystemFunction
title: GetGeneratorSystemFunction işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GetGeneratorSystemFunction
qsharp.summary: Retrieves the `GeneratorIndex` function in a `GeneratorSystem`.
ms.openlocfilehash: 60ebbdbd1020d41a54426377043fc0c84ceec504
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733535"
---
# <a name="getgeneratorsystemfunction-function"></a>GetGeneratorSystemFunction işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


`GeneratorIndex`İçindeki işlevini alır `GeneratorSystem` .

```qsharp
function GetGeneratorSystemFunction (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex)
```


## <a name="input"></a>Giriş

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`İlgi çekici.



## <a name="output--int---generatorindex"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int) -> [generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex`Hamiltonian içindeki her terimi dizine alan bir işlev.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. simülasyon. Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)
- [Microsoft. hisse. simülasyon. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)