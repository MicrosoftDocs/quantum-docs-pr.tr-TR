---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: ReflectAboutInteger işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730578"
---
# <a name="reflectaboutinteger-operation"></a>ReflectAboutInteger işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Leyebilir [](https://nuget.org/packages/)


Belirli bir klasik tamsayı hakkında hisse bir kayıt yansıtır.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Açıklama

Başlangıçta $ \ sum_i \ alpha_i \ket{i} $ durumunda bir hisse kayıt verildi her $ \ket{i} $, bir tamsayıyı temsil eden temel bir durumdur $i $, belirli bir tamsayı $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {ij}} \ alpha_i \ket{i} $ $ gibi kaydın durumunu yansıtır.

## <a name="input"></a>Giriş

### <a name="index--int"></a>Dizin: [Int](xref:microsoft.quantum.lang-ref.int)

Klasik tamsayı dizin oluşturma ile ilgili temel durumu oluşturur.


### <a name="reg--littleendian"></a>reg: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlem, ek yardımcı qubits 'in açıkça ayrılması gerekmeden yerinde uygulanır.