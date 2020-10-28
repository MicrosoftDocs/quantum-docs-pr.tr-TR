---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727283"
---
# <a name="dumpoperation-operation"></a>DumpOperation işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Leyebilir [](https://nuget.org/packages/)


Bir işlem verildiğinde, geçerli yürütme hedefi tarafından kullanılabilir hale getirilen işlem hakkındaki tanılamayı görüntüler.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Verilen işlemin işlem gördüğü qubit sayısı.


### <a name="op--qubit--unit-adj"></a>Op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama

Tanılanmakta olan işlem.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlemin çağrılması, Q # içinden herhangi bir observable etkiye sahip değildir. Varsa, görüntülenen tam Tanılamalar geçerli yürütme hedefi ve düzenleyici ortamına bağımlıdır.
Örneğin, tam durum hisse benzeticisinde kullanıldığında, göstermek için kullanılan bir Unitary matrisi `op` görüntülenir.

Simülatörleri üzerinde çalıştırıldığında, bir genel aşama belirsizliğin (örneğin, tam durum simülatörü), döndürülen temsiller genel bir aşamaya kadar farklılık gösterebilir.

Benzer şekilde, satır ve sütun matris temsilinin sıralaması, bu işlemi destekleyen her simülatör tarafından kullanılan kurallara göre farklılık gösterebilir.