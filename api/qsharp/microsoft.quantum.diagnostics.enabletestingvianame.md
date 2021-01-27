---
uid: Microsoft.Quantum.Diagnostics.EnableTestingViaName
title: EnableTestingViaName Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EnableTestingViaName
qsharp.summary: Compiler-recognized attribute via which an alternative name can be defined that may be used when loading a type or callable for testing purposes.
ms.openlocfilehash: c488b6f3d22fd0c6d4e950070464e914f757654c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853376"
---
# <a name="enabletestingvianame-user-defined-type"></a>EnableTestingViaName Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Bir tür yüklenirken veya test amaçlı olarak çağrılabilir şekilde kullanılabilecek alternatif bir adın tanımlanabilmesi için, derleyici tarafından tanınan öznitelik.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype EnableTestingViaName = (String);
```

