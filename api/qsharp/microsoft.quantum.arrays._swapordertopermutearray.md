---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846285"
---
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Sıralı bir dizi oluşturmak için bir dizideki sıralama öğelerinin takas edilmesi gereken sırası döndürür.
Değiştirmeleri bir yerde gerçekleşir.

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>Giriş

### <a name="neworder--int"></a>newOrder: [Int](xref:microsoft.quantum.lang-ref.int)[]

Yeni dizinin dizinlerinin permütasyoniyle dizi. $N $ öğe olmalıdır, her biri $0 $ ile $n-$1 arasında benzersiz bir tamsayıdır.



## <a name="output--intint"></a>Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Kayıt düzeni, takas edilecek iki dizini temsil eder. Takas eden en düşük dizinde başlar.

## <a name="example"></a>Örnek

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a>Açıklamalar

## <a name="psuedocode"></a>Psuedocode

için (Dizin 0.. length (newOrder)-1) {while newOrder [Dizin]! = Dizin {Switch newOrder [Dizin] ile newOrder [Dizin]]}}