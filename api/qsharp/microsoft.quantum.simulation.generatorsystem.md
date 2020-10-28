---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem Kullanıcı tanımlı türü
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733538"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem Kullanıcı tanımlı türü

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Leyebilir [](https://nuget.org/packages/)


Bir es koleksiyonunu temsil eder `GeneratorIndex` .

Tek Dizin tamsayı kullanarak bu koleksiyonu yineliyoruz ve koleksiyonun boyutunun bilindiği varsayılır.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Açıklamalar

Örnekleri `GeneratorSystem` , işlevi kullanılarak kolayca tanımlanabilir <xref:microsoft.quantum.arrays.lookupfunction> .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)