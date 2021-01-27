---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829271"
---
# <a name="dumpoperation-operation"></a>DumpOperation işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Bir işlem verildiğinde, geçerli yürütme hedefi tarafından kullanılabilir hale getirilen işlem hakkındaki tanılamayı görüntüler.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Verilen işlemin işlem gördüğü qubit sayısı.


### <a name="op--qubit--unit--is-adj"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Tanılanmakta olan işlem.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Örnek

Hisse Benzetici hedefi üzerinde çalıştırıldığında, aşağıdaki kod parçacığı $ $ \begin{aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{Matrix}\right) \end{aligned} matrisini çıktı.
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a>Açıklamalar

Bu işlemin çağrılması, Q # içinden herhangi bir observable etkiye sahip değildir. Varsa, görüntülenen tam Tanılamalar geçerli yürütme hedefi ve düzenleyici ortamına bağımlıdır.
Örneğin, tam durum hisse benzeticisinde kullanıldığında, göstermek için kullanılan bir Unitary matrisi `op` görüntülenir.

Simülatörleri üzerinde çalıştırıldığında, bir genel aşama belirsizliğin (örneğin, tam durum simülatörü), döndürülen temsiller genel bir aşamaya kadar farklılık gösterebilir.

Benzer şekilde, satır ve sütun matris temsilinin sıralaması, bu işlemi destekleyen her simülatör tarafından kullanılan kurallara göre farklılık gösterebilir.