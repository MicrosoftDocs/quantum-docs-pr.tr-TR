---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853067"
---
# <a name="steanecode-function"></a>SteaneCode işlevi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yerinde sendromu ölçümünde ⟦ 7, 1, 3 ⟧ steane Code Encoder ve Decoder 'ı temsil eden bir CSS değeri döndürür.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Çıkış: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

⟦ 7, 1, 3 ⟧ Steane kodu için kodlama ve hata düzeltme gerçekleştirmek üzere tüm ilgili verileri toplayan CSS türünde bir nesne.

## <a name="remarks"></a>Açıklamalar

Bu kod aşağıdaki kağıda bulundu:

- A. Steane, "çoklu parçacık girişim ve hisse hata düzeltmesi", proc. Roy. SOC. lond. A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.