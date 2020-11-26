---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Ayrılan Defromsteanecode işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 50fc6fb22e8b65ce10aba41e18362ad96236a907
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201147"
---
# <a name="decodefromsteanecode-operation"></a>Ayrılan Defromsteanecode işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


⟦ 7, 1, 3 ⟧ Steane hisse kodu altında, kodlanmamış bir hisse CIL kaydını kodlanmış bir hisse kaydına eşleyen ters kodlama işlemi.

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Giriş

### <a name="logicalregister--logicalregister"></a>logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Kodlanmış 5-qubit kodu mantıksal durumunu temsil eden bir qubits dizisi.



## <a name="output--qubitqubit"></a>Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])

İkinci parametrede yardımcı qubits ile birlikte ilk parametrede kodlanmamış durumu temsil eden bir qubit dizisi 1 uzunluğunda bir dizi.

## <a name="remarks"></a>Açıklamalar

Seçilen kod çözücüsü, ⟦ 7, 1, 3 ⟧ Steane kodunun CSS Code özelliğini kullanır, yani X hatalarını ve Z hatalarını ayrı olarak düzeltir. Kodun bir özelliği, sırasıyla x, sırasıyla z özelliğinin, bir tamsayı kabul edildiğinde x, z sendromu 'nin 3 bitlik kodlamasıdır.

## <a name="references"></a>Başvurular

- D. Gottesman, "sabitleyici kodlar ve hisse hata düzeltmesi," Ph.D. sıra, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Errordüzeltmesini. SteaneCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [Microsoft. hisse. Errordüzeltmesini. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [Microsoft. hisse. Errordüzeltmesini. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)