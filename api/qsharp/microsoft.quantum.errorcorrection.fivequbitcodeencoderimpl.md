---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Fivequbitcodeencoderımpl işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727056"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>Fivequbitcodeencoderımpl işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Leyebilir [](https://nuget.org/packages/)


Hem 5 qubit Kodlayıcı hem de kod çözücü uygulamak için kullanılan özel işlem.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="data--qubit"></a>veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Giriş qubit olan 1 qubit tutan bir dizi.


### <a name="scratch--qubit"></a>karalama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

artıklık ekleyen 4 qubit tutan bir dizi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Seçilen belirli bir kodlayıcı, V. Kliuchnikov ve D. Maslov, "Clifford devreleri," fiziksel. Rev. fiziksel. Rev. A 88, 052307 (2013) ' den alınmıştır. https://arxiv.org/abs/1305.0810, Şekil 4b) ve toplam 11 kapı gerektirir.