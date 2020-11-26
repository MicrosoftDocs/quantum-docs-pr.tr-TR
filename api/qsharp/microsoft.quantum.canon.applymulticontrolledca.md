---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 28797583c23e21eb4bcae996a34c70ee06c6dbe8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209290"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Listedir denetimli bir işlemin çarpma denetimli bir sürümünü uygular.
Değiştirici, `CA` tek qubit işleminin denetlenebilir ve adjointable olduğunu gösterir.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="singlycontrolledop--qubit--unit--is-adj"></a>Singlycontroltadop: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfastı

Tek bir qubit üzerinde denetlenen bir işlem.
İşlemin bağımsız değişkenindeki ilk qubit bir denetim olarak kabul edilir ve REST 'in hedef qubit olduğu varsayılır.
`ApplyMultiControlled` her zaman `singlyControlledOp` en az 1 uzunluğunda bir bağımsız değişkenle çağırır.


### <a name="ccnot--ccnotop"></a>ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)

Oluşturma için kullanılacak kontrollü kontrollü olmayan ağ geçidi.


### <a name="controls--qubit"></a>denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

`singlyControlledOp`Üzerinde kontrol edilecek qubits.
Uzunluğu `controls` en az 1 olmalıdır.


### <a name="targets--qubit"></a>hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Üzerinde davranan hedef qubit `singlyControlledOp` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlem yalnızca temiz bir anyenla qubit kullanır.

Açıklama ve devre diyagramı için bkz. Şekil 4,10, Bölüm 4,3, Nielsen & Chuang

## <a name="references"></a>Başvurular

- [*Michael A. Nielsen, Isaac L. Chuang*, hisse hesaplaması ve hisse bilgisi](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)