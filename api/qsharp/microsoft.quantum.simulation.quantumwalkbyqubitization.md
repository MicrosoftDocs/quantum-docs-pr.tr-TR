---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: Miktar Tumwalkbyqubitişleştirme işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ccef1bbf400e01800053777d0010acb7addaef53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192494"
---
# <a name="quantumwalkbyqubitization-function"></a>Miktar Tumwalkbyqubitişleştirme işlevi

Ad alanı: [Microsoft. hisse. benzetim](xref:Microsoft.Quantum.Simulation)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Blok kodlama yansımasını bir hisse mühendisiye dönüştürür.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Açıklama

Belirli bir `BlockEncodingReflection` operatör $H $ ' i kodlayan bir Unitary $U $ tarafından temsil edilen bir işlem, bu dosyayı $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ alanını içeren bir hisse alım $W $ değerine dönüştürür.

## <a name="input"></a>Giriş

### <a name="blockencoding--blockencodingreflection"></a>Blockenkodlama: [Blockencodingreflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`Hisse için bir $U $.



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Çıkış: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Bir hisse alım $W $, Yazmaçlarda ortaklaşa bulunan `a` ve `s` Bu blok-kodlama $H $ ve $ \pm e ^ {\pm i\sin ^ {-1} (H)} $ yelpazesini içerir.

## <a name="references"></a>Başvurular

- Hamiltonian simülasyonu, Qubitiş, Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. simülasyon. Blockenkodlama](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. hisse. simülasyon. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)