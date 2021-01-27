---
uid: Microsoft.Quantum.Synthesis.Extended
title: Genişletilmiş işlev
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855468"
---
# <a name="extended-function"></a>Genişletilmiş işlev

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir tayfı ters katsayılar ile genişletir

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>Giriş

### <a name="spectrum--int"></a>SPIN: [Int](xref:microsoft.quantum.lang-ref.int)[]

Spectral katsayıları



## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

Katsayıların ardından ters kopya

## <a name="example"></a>Örnek

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```