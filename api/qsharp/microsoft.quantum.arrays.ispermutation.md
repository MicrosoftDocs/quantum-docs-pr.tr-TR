---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermütasyon işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848087"
---
# <a name="ispermutation-function"></a>Ispermütasyon işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yalnızca belirli bir dizi bir permütasyon temsil ediyorsa, true verir.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Description

Bir dizi `array` uzunluk verildiğinde `n` , ve yalnızca her bir tamsayı ' `0` `n - 1` de tam olarak bir kez görünüyorsa true, ancak `array` `array` öğeler üzerinde bir permütasyon olarak yorumlanabilecek şekilde döndürür `n` .

## <a name="input"></a>Giriş

### <a name="permuation--int"></a>permütasyon: [Int](xref:microsoft.quantum.lang-ref.int)[]

Bir permütasyon temsil eden veya temsil eden bir dizi.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="example"></a>Örnek

Aşağıdaki Q # kodu "tüm Tanılamalar başarıyla tamamlandı" iletisini yazdırır:

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>Açıklamalar

Sıfır uzunluklu bir dizi, önemli ölçüde bir permütasyon.