---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: df00c7572d909a67ec658bc8dccaf0e338afe5c5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200756"
---
# <a name="knilldistill-operation"></a>KnillDistill işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Knill Magic State deneyimlerinin algoritmasını uygular.

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>Açıklama

Bir sihirli durum $ $ \begin{hizalaması} \cos\frac{\pi} {8} {0} \tus+ \sin \ FRAC{\pi} {8} \kovaryans {1} \ End{hizalaması}, $ $ ' nin yaklaşık 15 ' i, daha yüksek kaliteli bir kopya veriyor.

## <a name="input"></a>Giriş

### <a name="roughmagic--qubit"></a>Kabaghmagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Bir sihirli durumun yaklaşık kopyalarını içeren on beş qubit kaydı. Bu geri yükleme yordamının aşağıdaki uygulaması, `roughMagic[0]` daha yüksek kaliteli bir kopya içerir ve kaydın geri kalanı $ \ket{00\cnoktalara 0} $ duruma sıfırlanır.



## <a name="output--bool"></a>Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)

`true`Daha sonra, başarılı olan yordam ve daha yüksek kaliteli kopya kabul edilmelidir. Eğer `false` yordam başarısız olursa ve kaydın durumu tanımsız olarak düşünülmelidir.

## <a name="remarks"></a>Açıklamalar

Knill algoritmasını izliyoruz.
Ancak, mevcut uygulama çok fazla qubit kullandığından en iyi şekilde sürer.
Sihirli durumlar bu yordama eklenir ve bu durumda daha iyi protokoller vardır.

## <a name="references"></a>Başvurular

- [Knill](https://arxiv.org/abs/quant-ph/0402171)