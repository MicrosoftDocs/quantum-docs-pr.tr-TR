---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 05a0e8110539742501883fea75ac368d9946164d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729759"
---
# <a name="andladder-operation"></a>AndLadder işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Hedef qubitleri kaydettirmek üzerinde denetimli bir "ve" el der "gerçekleştirir.

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="description"></a>Açıklama

Bu işlem, aşağıdaki hesaplama tabanlı eşleme tarafından tanımlanan bir dönüşüm uygular, $ $ \begin{hizalaması} \ket{x \_ 1, \noktalar, x \_ n} \ket{y \_ 1, \noktalar, y \_ {n-1}} \mapsto \ket{x \_ 1, \noktalar, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \noktalar, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cnoktalar \land x \_ {n-1}}, \end{hizalaması} $ $, $ \ket{x \_ 1, \noktalar, x \_ n} $, ' nin hesaplama tabanlı durumlarına `controls` ve $ \ket{y \_ 1, \noktalar, y \_ {n-1}} $ öğesinin hesaplama tabanlı durumlarına başvurur `targets` .

## <a name="input"></a>Giriş

### <a name="ccnot--ccnotop"></a>ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)

Oluşturma için kullanılacak CCNOT kapısı.


### <a name="controls--qubit"></a>denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ve merdiveni için denetim olarak kullanılacak qubit kaydı.
Bu işlem, sabit durum hesaplama durumlarını bırakır `controls` .
Uzunluğu `controls` en az 2 olmalı ve uzunluğu ve uzunluğuna eşit olmalıdır `targets` .


### <a name="targets--qubit"></a>hedefler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Uzunluğu `targets` en az 1, eksi bir uzunluk uzunluğuna eşit olmalıdır `controls` .



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

- Ve ' ın bir parçası olarak kullanılır <xref:microsoft.quantum.canon.applymulticontrolledc> <xref:microsoft.quantum.canon.applymulticontrolledca> .
- Açıklama ve devre diyagramı için, bkz. Şekil 4,10, Bölüm 4,3, Nielsen & Chuang.

## <a name="references"></a>Referanslar

- [*Michael A. Nielsen, Isaac L. Chuang* , hisse hesaplaması ve hisse bilgisi](http://doi.org/10.1017/CBO9780511976667)