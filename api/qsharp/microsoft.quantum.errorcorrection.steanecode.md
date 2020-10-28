---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726990"
---
# <a name="steanecode-function"></a>SteaneCode işlevi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Leyebilir [](https://nuget.org/packages/)


Yerinde sendromu ölçümünde ⟦ 7, 1, 3 ⟧ steane Code Encoder ve Decoder 'ı temsil eden bir CSS değeri döndürür.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Çıkış: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

⟦ 7, 1, 3 ⟧ Steane kodu için kodlama ve hata düzeltme gerçekleştirmek üzere tüm ilgili verileri toplayan CSS türünde bir nesne.

## <a name="remarks"></a>Açıklamalar

Bu kod aşağıdaki kağıda bulundu:

- A. Steane, "çoklu parçacık girişim ve hisse hata düzeltmesi", proc. Roy. SOC. lond. A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.