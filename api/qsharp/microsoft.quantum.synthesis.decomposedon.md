---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: 79f952e7bc7ba9f5337cf5e7a625e0d270a2e17a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203239"
---
# <a name="decomposedon-function"></a>DecomposedOn işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

