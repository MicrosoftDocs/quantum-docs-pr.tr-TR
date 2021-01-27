---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: dbbbb2b67dcf191c74e593f61eb894192acb4d48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854722"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a>TimeDependentGeneratorSystem Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zamana bağlı bir dinamik üreticisini, zaman içinde dinamik oluşturucusunun değerine kadar bir işlev olarak temsil eder.

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

