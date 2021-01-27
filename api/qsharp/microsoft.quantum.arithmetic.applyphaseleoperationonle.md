---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: d94fdb55e051e76dd518eff14b80d1a24516bf8a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843672"
---
# <a name="applyphaseleoperationonle-operation"></a>ApplyPhaseLEOperationOnLE işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


<xref:microsoft.quantum.arithmetic.littleendian>Türünde bir hedef kayıt üzerinde giriş olarak kayıt alan bir işlem uygular <xref:microsoft.quantum.arithmetic.phaselittleendian> .

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Giriş

### <a name="op--phaselittleendian--unit"></a>Op: [phaselittliendian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [birimi](xref:microsoft.quantum.lang-ref.unit) 

Uygulanacak işlem.


### <a name="target--littleendian"></a>Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

İşlemin uygulandığı kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Kayıt, kullanılarak öğesine dönüştürülür `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> ve öğesinden sonra özgün gösterimine döndürülür `op` .

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. Applyphaseleoperationontaa](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Microsoft. hisse. Canon. Applyphaseleoperationontaa](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Microsoft. hisse. Canon. Applyphaseleoperationontaca](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)