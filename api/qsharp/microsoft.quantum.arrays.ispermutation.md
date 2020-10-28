---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermütasyon işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730175"
---
# <a name="ispermutation-function"></a>Ispermütasyon işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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