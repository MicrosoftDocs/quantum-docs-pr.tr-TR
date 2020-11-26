---
uid: Microsoft.Quantum.Diagnostics.Test
title: Test Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 80821cb46d773d84085838d9ee539a8a45c43e61
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201504"
---
# <a name="test-user-defined-type"></a>Test Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Derleyici tarafından tanınan öznitelik bir birim testini işaretlemek için kullanılır.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="executiontarget--string"></a>ExecutionTarget: [dize](xref:microsoft.quantum.lang-ref.string)

