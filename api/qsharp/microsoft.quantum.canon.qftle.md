---
uid: Microsoft.Quantum.Canon.QFTLE
title: QFTLE işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 893366833e5bd6b358884c11f4534609efd72d24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852270"
---
# <a name="qftle-operation"></a>QFTLE işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Küçük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="qs--littleendian"></a>QS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Hisse kayıt defteri



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Giriş ve çıkışın little endian kodlamada olduğu varsayılır.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)