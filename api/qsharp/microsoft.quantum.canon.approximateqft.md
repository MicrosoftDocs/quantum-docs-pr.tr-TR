---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Yaklaşık Teqft işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: ffa3a3737a43fbe6acc57700ae122a13586482e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728958"
---
# <a name="approximateqft-operation"></a>Yaklaşık Teqft işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Yaklaşık hisse Fourier dönüştürmesinin (AQFT) bir hisse kaydına uygulanmasını sağlar.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
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

## <a name="references"></a>Referanslar

- [*A. Roetteler, TH. Beth* , Uyg. Algeköşeli eng. Commun. Bilgi. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arxıv: Quant-pH/sper1067v1](https://arxiv.org/abs/quant-ph/0201067)