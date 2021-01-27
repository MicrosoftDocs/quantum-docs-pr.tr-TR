---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853149"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode işlevi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yerinde sendromu ölçümlü ⟦ 5, 1, 3 ⟧ Code Encoder ve Decoder öğelerini temsil eden bir qecc değeri döndürür.

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>Çıkış: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Bir tür belirterek hisse hata düzeltme kodunun bir uygulamasını döndürür `QECC` .

## <a name="remarks"></a>Açıklamalar

Bu kod, aşağıdaki iki İnceleme içinde bağımsız olarak bulunur:

- C. Olsun. Bennett, D. DiVincenzo, J. A. Smolin ve W. K. Wootters, "karışık durum entanglement ve hisse hata düzeltmesi," fiziksel. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 ve
- Sağ. LaFlamme, C. Miquel, J. P. Paz ve W. H. Zurek, "kusursuz hisse hata düzeltme kodu," fiziksel. Rev. lett. 77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019