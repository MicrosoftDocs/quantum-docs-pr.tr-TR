---
uid: Microsoft.Quantum.Canon.QFT
title: QFT işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 30f475c3850c248b5af58db1e4aac3638c4c0471
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852288"
---
# <a name="qft-operation"></a>QFT işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Büyük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="qs--bigendian"></a>QS: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Hisse kayıt defteri



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Giriş ve çıkışın big endian kodlamada olduğu varsayılır.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applynicetumoniertransformto](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)