---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: acaa563245bb7c701316d2dfd35b5be03d8e024d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843719"
---
# <a name="applyoutercdkmadder-operation"></a>ApplyOuterCDKMAdder işlemi

Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aşağıdaki tamsayı ekleme işleminde kullanılan, geri döndürülebilir ve yerinde Ripple-taşıma işlemi aşağıda verilmiştir.
İki qubit kaydı `xs` ve `ys` aynı uzunlukta olmak üzere, bu işlem, içindeki QUBIT 'ler içeren bir RIPPLE ve ccnot kapısı sırası uygular ve bu, `xs` `ys` hedef olarak içinde denetimler ve qubits olarak sunulur `xs` .

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="xs--littleendian"></a>xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

İlk qubit kayıt, denetimleri ve hedefleri içerir.


### <a name="ys--littleendian"></a>YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

, Denetimlere katkıda bulunan ikinci qubit kayıt.


### <a name="ancilla--qubit"></a>anyalanla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Bu işleme, Ripptacarryaddercdkm içinde kullanılan anella qubit.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Başvurular

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutın, David Petrie Moulton: "yeni bir 2004 hisse
  https://arxiv.org/abs/quant-ph/0410184v1