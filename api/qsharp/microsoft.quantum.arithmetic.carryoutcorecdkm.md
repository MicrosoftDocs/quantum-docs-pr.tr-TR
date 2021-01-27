---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Carrzı Corecdkm işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 2065c767b341241d32e5ac06bcff0071cbadb266
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843338"
---
# <a name="carryoutcorecdkm-operation"></a>Carrzı Corecdkm işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


En yukarıdaki ApplyOuterCDKMAdder işlemiyle birlikte kullanılan Rippmacarryaddercdkm içindeki temel işlem, yani Ripplicarryaddercdkm 'nin iç işlemini elde etmek için bu işlemle birlikte kullanılır. Bu işlem, alma qubit ' i hesaplar ve girişin bir bölümünde bir kapı yok dizisi uygular `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
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



## <a name="references"></a>Başvurular

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse
  https://arxiv.org/abs/quant-ph/0410184v1