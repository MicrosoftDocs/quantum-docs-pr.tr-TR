---
uid: Microsoft.Quantum.Core.Deprecated
title: Kullanım dışı Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832077"
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