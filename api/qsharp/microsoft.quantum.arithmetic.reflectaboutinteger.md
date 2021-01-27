---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: 4d451c4e8e002f86c892b394f58ea2d7e9dd6a48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842987"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Belirli bir klasik tamsayı hakkında hisse bir kayıt yansıtır.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Başlangıçta $ \ sum_i \ alpha_i \ket{i} $ durumunda bir hisse kayıt verildi her $ \ket{i} $, bir tamsayıyı temsil eden temel bir durumdur $i $, belirli bir tamsayı $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $ gibi kaydın durumunu yansıtır.

## <a name="input"></a>Giriş

### <a name="index--int"></a>Dizin: [Int](xref:microsoft.quantum.lang-ref.int)

Klasik tamsayı dizin oluşturma ile ilgili temel durumu oluşturur.


### <a name="reg--littleendian"></a>reg: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlem, ek yardımcı qubits 'in açıkça ayrılması gerekmeden yerinde uygulanır.