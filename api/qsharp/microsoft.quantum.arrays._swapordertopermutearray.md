---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221717"
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

## <a name="remarks"></a>Açıklamalar

## <a name="psuedocode"></a>Psuedocode

için (Dizin 0.. length (newOrder)-1) {while newOrder [Dizin]! = Dizin {Switch newOrder [Dizin] ile newOrder [Dizin]]}}