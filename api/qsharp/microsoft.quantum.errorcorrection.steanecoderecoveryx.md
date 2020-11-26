---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 5fac832ef5b7d7be2d85675a32f45e66312f66c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200381"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX işlevi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦ 7, 1, 3 ⟧ Steane hisse kodu için bir sabitleyici grubunun X bölümü için kod çözücü.

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>Giriş

### <a name="syndrome--syndrome"></a>sendromu: [sendromu](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Sabitleştirici X bölümünü ölçerek elde edilen bir Sendromu dizisi.



## <a name="output--pauli"></a>Çıkış: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Kodlanmış hisse sisteme uygulandığında öğesine karşılık gelen hatayı düzelten Pauli işlemleri dizisi `syndrome` .

## <a name="remarks"></a>Açıklamalar

Seçilen kod çözücüsü, ⟦ 7, 1, 3 ⟧ Steane kodunun CSS Code özelliğini kullanır, yani X hatalarını ve Z hatalarını ayrı olarak düzeltir. Kodun bir özelliği, sırasıyla x, sırasıyla z özelliğinin, bir tamsayı kabul edildiğinde x, z sendromu 'nin 3 bitlik kodlamasıdır.

## <a name="references"></a>Başvurular

- D. Gottesman, "sabitleyici kodlar ve hisse hata düzeltmesi," Ph.D. sıra, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. hisse. Errordüzeltmesini. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)