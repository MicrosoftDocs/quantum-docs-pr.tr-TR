---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem Kullanıcı tanımlı türü
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225236"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir es koleksiyonunu temsil eder `GeneratorIndex` .

Tek Dizin tamsayı kullanarak bu koleksiyonu yineliyoruz ve koleksiyonun boyutunun bilindiği varsayılır.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Açıklamalar

Örnekleri `GeneratorSystem` , işlevi kullanılarak kolayca tanımlanabilir <xref:microsoft.quantum.arrays.lookupfunction> .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)