---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: Flipmaskelerin işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859257"
---
# <a name="flipmasks-function"></a>Flipmaskelerin işlevi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Her 2 düzeyi Unitary için, karşılık gelen 1-qubit kapısı uygulandıktan önce ve sonra ters çevrilmelidir.
Kolaylık sağlaması için 0 ile sonuç elde edin.

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a>Giriş

### <a name="decomposition--complexintint"></a>ayrıştırma: ([Complex](xref:Microsoft.Quantum.Math.Complex)[] [],[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="allqubitsmask--int"></a>allQubitsMask: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]

