---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 31b957a435c3f578bc03d432609cde14c2ef5ced
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728070"
---
# <a name="_computejordanwignerbitstring-function"></a>_ComputeJordanWignerBitString işlevi

Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Leyebilir [](https://nuget.org/packages/)


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