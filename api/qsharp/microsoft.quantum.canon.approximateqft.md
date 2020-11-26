---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Yaklaşık Teqft işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 97a410133e80cc5bffc810e9d6455baaee32364b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207709"
---
# <a name="approximateqft-operation"></a>Yaklaşık Teqft işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yaklaşık hisse Fourier dönüştürmesinin (AQFT) bir hisse kaydına uygulanmasını sağlar.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="a--int"></a>y: [Int](xref:microsoft.quantum.lang-ref.int)

en fazla parametre, QFT devresi içinde gerçekleşen kontrol edilen Z-döndürme işleminin ayıklandığını belirler.

Bir ∈ {0.. n} ve k>a 'nın QFT devresi öğesinden kaldırıldığı tüm Z-Rod 'ler 2π/2k 'nin ayıklama düzeyini belirten bir parametre. K >= log ₂ (n) + log ₂ (1/ε) + 3 ' ün bağlanabilir olduğu bilinmektedir | | QFT-AQFT | |<ε.


### <a name="qs--bigendian"></a>QS: [Bigenyen](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Yaklaşık ortalama Fourier dönüştürmesinin uygulandığı n qubit 'in hisse kaydı.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

AQFT, 2π/2k ve Hadamard Gates biçimindeki Z-dönüşü geçitleri gerektirir.

Giriş ve çıkışın big endian kodlamada kodlandığını kabul edilir.

## <a name="references"></a>Başvurular

- [*A. Roetteler, TH. Beth*, Uyg. Algeköşeli eng. Commun. Bilgi. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arxıv: Quant-pH/sper1067v1](https://arxiv.org/abs/quant-ph/0201067)