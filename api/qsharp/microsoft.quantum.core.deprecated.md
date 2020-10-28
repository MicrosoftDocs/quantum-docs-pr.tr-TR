---
uid: Microsoft.Quantum.Core.Deprecated
title: Kullanım dışı Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727458"
---
# <a name="deprecated-user-defined-type"></a>Kullanım dışı Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Core](xref:Microsoft.Quantum.Core)

Leyebilir [](https://nuget.org/packages/)


Derleyiciyi tanınan bir tür veya çağrılabilir olarak işaretlemek için kullanılan öznitelik.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="newname--string"></a>YeniAd: [dize](xref:microsoft.quantum.lang-ref.string)

Bunun yerine kullanılacak türün tam adı veya çağrılabilir.
Bir tür veya çağrılabilir bir değiştirme olmadan kullanımdan kalkmışsa boş dizeye ayarlanır.