---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733914"
---
# <a name="decomposedon-function"></a>DecomposedOn işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Leyebilir [](https://nuget.org/packages/)


Bir değişken üzerinde bir permütasyon 'yi kaldırır

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Açıklama

Bir permütasyon $ \pı $ ( `perm` ) ve bir dizin $i $ () verildiğinde `index` , bu yöntem, $ \ pi_l $ ve $ \ pi_r $ görüntülerinin $i $ ve $ \pi ' $ görüntüleri dışındaki dizinlerde bulunan öğelerinde bit değiştirmelerini sağlayan üç permütasyon $ ((\ pi_l, \ pi_r), \pı ') $ döndürür.

## <a name="input"></a>Giriş

### <a name="perm--int"></a>izin: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>Dizin: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Çıkış: (([Int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])

