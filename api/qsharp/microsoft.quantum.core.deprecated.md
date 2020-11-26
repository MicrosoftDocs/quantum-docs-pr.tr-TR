---
uid: Microsoft.Quantum.Core.Deprecated
title: Kullanım dışı Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224097"
---
# <a name="deprecated-user-defined-type"></a>Kullanım dışı Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Derleyiciyi tanınan bir tür veya çağrılabilir olarak işaretlemek için kullanılan öznitelik.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="newname--string"></a>YeniAd: [dize](xref:microsoft.quantum.lang-ref.string)

Bunun yerine kullanılacak türün tam adı veya çağrılabilir.
Bir tür veya çağrılabilir bir değiştirme olmadan kullanımdan kalkmışsa boş dizeye ayarlanır.