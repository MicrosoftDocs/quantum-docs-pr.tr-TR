---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839521"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString işlevi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Bir fermıonic işlecinde, çift sayıda oluşturma/himaılasyon işleçlerine sahip fermıon dizinleri arasında Ürdün Mııner dizesinin Z bileşenini hesaplar.

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a>Giriş

### <a name="nfermions--int"></a>nFermions: [Int](xref:microsoft.quantum.lang-ref.int)

Sistemdeki fermıons sayısı.


### <a name="idxfermions--int"></a>ıdxfermions: [Int](xref:microsoft.quantum.lang-ref.int)[]

fermıonic işleç dizinleri.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Uygulanacağı bit dizesi `Bool[]` `true` `PauliZ` .

## <a name="example"></a>Örnek

Let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]); bitString [false, false, false, true, true, true, false].