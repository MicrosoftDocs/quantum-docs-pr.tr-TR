---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727134"
---
# <a name="applybitflipencoder-operation"></a>ApplyBitFlipEncoder işlemi

Ad alanı: [Microsoft. hisse. Errordüzeltmesini](xref:Microsoft.Quantum.ErrorCorrection)

Leyebilir [](https://nuget.org/packages/)


Hem bit çevir Kodlayıcısı hem de kod çözücü uygulamak için kullanılan özel işlem.

Bu kodlayıcı, ' nin ilk durumu tarafından tanımlanan hatanın "Neden" olması durumunda, yerinde tutarlı kurtarmanın kullanılabilir olmasını sağlayabilir `auxQubits` .
Özellikle `auxQubits` $ \tus$ durumunda başlangıçta {10} Bu durum, kodlanmış qubit üzerinde $X _1 $ hatasına neden olur.

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Giriş

### <a name="coherentrecovery--bool"></a>Tutarlı Entrecovery: [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="data--qubit"></a>veri: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="scratch--qubit"></a>karalama: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referanslar

- DOI: 10.1103/PhysRevA. 85.044302