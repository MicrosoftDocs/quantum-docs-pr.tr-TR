---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856125"
---
# <a name="maybechooseelement-operation"></a>MaybeChooseElement işlemi

Ad alanı: [Microsoft. hisse. Random](xref:Microsoft.Quantum.Random)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Veri dizisi ve dizinleri üzerinde bir dağıtım verildiğinde, rastgele bir öğe seçme girişiminde bulunur.

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>Giriş

### <a name="data--t"></a>veri: 'T []

Bir öğenin seçilmesi gereken dizi.


### <a name="indexdistribution--discretedistribution"></a>ındexdistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Dizinleri üzerinden bir dağıtım `data` .



## <a name="output--boolt"></a>Çıkış: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="example"></a>Örnek

Aşağıdaki Q # parçacığı bir diziden rastgele bir öğe seçer:

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```