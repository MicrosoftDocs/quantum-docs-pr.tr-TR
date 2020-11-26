---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Fivequbitcodeencoderımpl işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: f70d2d1352c7b2eebee7a863eba97d78d7351dab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200858"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>Fivequbitcodeencoderımpl işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Hem 5 qubit Kodlayıcı hem de kod çözücü uygulamak için kullanılan özel işlem.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Giriş

### <a name="data--qubit"></a>veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Giriş qubit olan 1 qubit tutan bir dizi.


### <a name="scratch--qubit"></a>karalama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

artıklık ekleyen 4 qubit tutan bir dizi.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Seçilen belirli bir kodlayıcı, V. Kliuchnikov ve D. Maslov, "Clifford devreleri," fiziksel. Rev. fiziksel. Rev. A 88, 052307 (2013) ' den alınmıştır. https://arxiv.org/abs/1305.0810, Şekil 4b) ve toplam 11 kapı gerektirir.