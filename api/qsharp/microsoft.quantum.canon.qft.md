---
uid: Microsoft.Quantum.Canon.QFT
title: QFT işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728478"
---
# <a name="qft-operation"></a>QFT işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Büyük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Giriş

### <a name="qs--bigendian"></a>QS: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Hisse kayıt defteri



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Giriş ve çıkışın big endian kodlamada olduğu varsayılır.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applynicetumoniertransformto](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)