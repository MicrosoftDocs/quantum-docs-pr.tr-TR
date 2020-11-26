---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202065"
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



## <a name="remarks"></a>Açıklamalar

Bu işlemin çağrılması, Q # içinden herhangi bir observable etkiye sahip değildir. Varsa, görüntülenen tam Tanılamalar geçerli yürütme hedefi ve düzenleyici ortamına bağımlıdır.
Örneğin, tam durum hisse benzeticisinde kullanıldığında, göstermek için kullanılan bir Unitary matrisi `op` görüntülenir.

Simülatörleri üzerinde çalıştırıldığında, bir genel aşama belirsizliğin (örneğin, tam durum simülatörü), döndürülen temsiller genel bir aşamaya kadar farklılık gösterebilir.

Benzer şekilde, satır ve sütun matris temsilinin sıralaması, bu işlemi destekleyen her simülatör tarafından kullanılan kurallara göre farklılık gösterebilir.