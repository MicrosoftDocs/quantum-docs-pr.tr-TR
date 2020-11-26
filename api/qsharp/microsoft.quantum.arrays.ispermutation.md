---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermütasyon işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220935"
---
# <a name="ispermutation-function"></a>Ispermütasyon işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yalnızca belirli bir dizi bir permütasyon temsil ediyorsa, true verir.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Açıklama

Bir dizi `array` uzunluk verildiğinde `n` , ve yalnızca her bir tamsayı ' `0` `n - 1` de tam olarak bir kez görünüyorsa true, ancak `array` `array` öğeler üzerinde bir permütasyon olarak yorumlanabilecek şekilde döndürür `n` .

## <a name="input"></a>Giriş

### <a name="permuation--int"></a>permütasyon: [Int](xref:microsoft.quantum.lang-ref.int)[]

Bir permütasyon temsil eden veya temsil eden bir dizi.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="remarks"></a>Açıklamalar

Sıfır uzunluklu bir dizi, önemli ölçüde bir permütasyon.