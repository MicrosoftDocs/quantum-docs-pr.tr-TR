---
uid: Microsoft.Quantum.Diagnostics.Test
title: Test Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 2f1b521c4ef2bf8e672ca4fe7a5f380d744300b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853264"
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

