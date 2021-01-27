---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Applynicetumon Iertransform işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844768"
---
# <a name="applyquantumfouriertransform-operation"></a>Applynicetumon Iertransform işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Küçük endian gösteriminde bir tamsayı içeren bir hisse kayıt üzerinde hisse Fourier dönüşümü gerçekleştirir.

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="qs--littleendian"></a>QS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Hisse kayıt defteri



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Giriş ve çıkışın little endian kodlamada olduğu varsayılır.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applynicetumoniertransformto](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)