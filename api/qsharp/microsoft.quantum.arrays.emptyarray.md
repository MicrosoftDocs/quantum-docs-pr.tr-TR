---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846168"
---
# <a name="emptyarray-function"></a>EmptyArray işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Verilen türdeki boş diziyi döndürür.

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>Çıkış: ' TElement []

Boş dizi.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="telement"></a>' TElement

Dizinin öğe türü.

## <a name="example"></a>Örnek

```qsharp
let empty = EmptyArray<Int>();
```