---
uid: Microsoft.Quantum.Diagnostics.EnableTestingViaName
title: EnableTestingViaName Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EnableTestingViaName
qsharp.summary: Compiler-recognized attribute via which an alternative name can be defined that may be used when loading a type or callable for testing purposes.
ms.openlocfilehash: 52ec8e670744586f85ee642b0e991734ff91afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201980"
---
# <a name="enabletestingvianame-user-defined-type"></a>EnableTestingViaName Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Bir tür yüklenirken veya test amaçlı olarak çağrılabilir şekilde kullanılabilecek alternatif bir adın tanımlanabilmesi için, derleyici tarafından tanınan öznitelik.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype EnableTestingViaName = (String);
```

