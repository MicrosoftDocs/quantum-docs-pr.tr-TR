---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Applyxcontroltadontruthtable işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: aa4e1bc0d5058228721728a894b896331ec626d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203306"
---
# <a name="applyxcontrolledontruthtable-operation"></a>Applyxcontroltadontruthtable işlemi

Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


@"microsoft.quantum.intrinsic.x" `target` `func` İçindeki klasik atama için Boolean işlevi true olarak değerlendirilirse, işlemini üzerine uygular `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

İşlem, sırasıyla $x $ ve $y $ temsil eden Unitary işlemini \begin{hizalaması} U\ket {x} \ demet {y} = \ket{x}\ket{y \oplus f (x)} \end{hizalaması} uygular `controlRegister` `target` .

$F $ Boole işlevi, büyük bir tamsayı bakımından bir Truth tablosu olarak temsil edilir.
Örneğin, üç giriş üzerindeki çoğunluk işlevi bitstring tarafından temsil edilir `11101000` . Bu, en önemli bitin `1` giriş atamasına karşılık geldiği `(1, 1, 1)` ve en az önemli bitin `0` giriş atamasına karşılık geldiği `(0, 0, 0)` bitdizedir.
`0xE8L`Onaltılık gösterimde veya ondalık gösteriminde olduğu gibi büyük tamsayı ile temsil edilebilir `232L` .  `L`Sonek, sabitin tür olduğunu gösterir `BigInt` .
Bu gösterim hakkında daha fazla ayrıntı aynı zamanda [Truth tabloları kükümi](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables)'da bulunabilir.

Uygulama ve kapıları kullanımını sağlar @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" .

## <a name="input"></a>Giriş

### <a name="func--bigint"></a>Func: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Büyük tamsayı olarak temsil edilen Boolean Truth tablosu


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Denetim qubits 'i kaydetme


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Hedef qubit



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Başvurular

- [*N. Schuch*, *J. Siewert*, PRL 91, no. 027902, 2003, arxıv: Quant-pH/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias Soeken*, *MARI Roetteler*, arxıv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Sengıı. Applyxcontroltadontruthtablewithcleantarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)