---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Identitygeneratorındex işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: b389ca1e0737463e6ccd5ce885b849c6b32d65d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844332"
---
# <a name="identitygeneratorindex-function"></a>Identitygeneratorındex işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Identity evrimu işlemine karşılık gelen sıfır Hamiltonian ile tutarlı bir Oluşturucu dizini döndürür `H = 0` .

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Giriş

### <a name="idxterm--int"></a>ıdxterm: [Int](xref:microsoft.quantum.lang-ref.int)

Bu giriş yok sayılır ve <xref:microsoft.quantum.simulation.generatorsystem> Kullanıcı tanımlı türle tutarlılık için tanımlanır.



## <a name="output--generatorindex"></a>Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Hamiltonian $H = $0 altında evrimi temsil eden bir Oluşturucu dizini.