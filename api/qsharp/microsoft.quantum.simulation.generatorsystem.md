---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem Kullanıcı tanımlı türü
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858420"
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