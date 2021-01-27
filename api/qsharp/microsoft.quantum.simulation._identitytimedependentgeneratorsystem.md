---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857994"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>_IdentityTimeDependentGeneratorSystem işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


`H(s) = 0`Bir zamanlama parametresi olduğu Hamiltonian ile tutarlı bir Oluşturucu sistemi döndürür `s` .

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Giriş

### <a name="schedule--double"></a>zamanlama: [Double](xref:microsoft.quantum.lang-ref.double)

Bu giriş yok sayılır ve <xref:microsoft.quantum.canon.timedependentgeneratorsystem> Kullanıcı tanımlı türle tutarlılık için tanımlanır.



## <a name="output--generatorsystem"></a>Çıkış: [Generatorsystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Tüm $s $ için Hamiltonian $H = $0 altında gelişleri temsil eden bir Oluşturucu sistemi.