---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Carrzı Corecdkm işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731639"
---
# <a name="carryoutcorecdkm-operation"></a>Carrzı Corecdkm işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


En yukarıdaki ApplyOuterCDKMAdder işlemiyle birlikte kullanılan Rippmacarryaddercdkm içindeki temel işlem, yani Ripplicarryaddercdkm 'nin iç işlemini elde etmek için bu işlemle birlikte kullanılır. Bu işlem, alma qubit ' i hesaplar ve girişin bir bölümünde bir kapı yok dizisi uygular `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

İlk qubit kayıt.


### <a name="ys--littleendian"></a>YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

İkinci qubit kaydı.


### <a name="ancilla--qubit"></a>anyalanla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Bu işleme, Ripptacarryaddercdkm içinde kullanılan anella qubit.


### <a name="carry--qubit"></a>taşır: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ripptacarryaddercdkm işleminde qubit ' i çalıştırır.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referanslar

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse
  https://arxiv.org/abs/quant-ph/0410184v1