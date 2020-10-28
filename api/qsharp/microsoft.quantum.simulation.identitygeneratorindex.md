---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: Identitygeneratorındex işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733527"
---
# <a name="identitygeneratorindex-function"></a>Identitygeneratorındex işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Identity evrimu işlemine karşılık gelen sıfır Hamiltonian ile tutarlı bir Oluşturucu dizini döndürür `H = 0` .

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Giriş

### <a name="idxterm--int"></a>ıdxterm: [Int](xref:microsoft.quantum.lang-ref.int)

Bu giriş yok sayılır ve <xref:microsoft.quantum.simulation.generatorsystem> Kullanıcı tanımlı türle tutarlılık için tanımlanır.



## <a name="output--generatorindex"></a>Çıkış: [Generatorındex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Hamiltonian $H = $0 altında evrimi temsil eden bir Oluşturucu dizini.