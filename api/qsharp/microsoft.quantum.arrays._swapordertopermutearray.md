---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730431"
---
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray işlevi

Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)

Leyebilir [](https://nuget.org/packages/)


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