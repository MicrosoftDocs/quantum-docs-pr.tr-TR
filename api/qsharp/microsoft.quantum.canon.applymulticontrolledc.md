---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: ApplyMultiControlledC işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: bf6b78cd18a827a9a4fd9d61dfd4d240de3503e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844861"
---
# <a name="applymulticontrolledc-operation"></a>ApplyMultiControlledC işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Listedir denetimli bir işlemin çarpma denetimli bir sürümünü uygular.
Değiştirici, `C` tek qubit işleminin denetlenebilir olduğunu gösterir.

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Giriş

### <a name="singlycontrolledop--qubit--unit"></a>Singlycontroltadop: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

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

- [Microsoft. hisse. Canon. ApplyMultiControlledCA](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)