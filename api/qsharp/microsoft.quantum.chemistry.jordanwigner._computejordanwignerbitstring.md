---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203952"
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