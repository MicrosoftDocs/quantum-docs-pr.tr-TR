---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733802"
---
# <a name="squarednorm-function"></a>SquaredNorm işlevi

Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)

Leyebilir [](https://nuget.org/packages/)


Bir vektörün kare 2-normini döndürür.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Açıklama

Bir vektörün kare 2-norm değerini döndürür; Yani, $ \vec{x} $ girişi verildiğinde $ \ sum_i x_i ^ 2 $ döndürür.

## <a name="input"></a>Giriş

### <a name="array--double"></a>dizi: [Double](xref:microsoft.quantum.lang-ref.double)[]

Kare 2-norm döndürülmek üzere olan vektör.



## <a name="output--double"></a>Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)

Kare 2-norm `array` .