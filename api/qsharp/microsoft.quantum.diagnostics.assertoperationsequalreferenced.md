---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 59c0fa72c9ca8f3bc512b6ed674fd73babc57f84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202320"
---
# <a name="assertoperationsequalreferenced-operation"></a>AssertOperationsEqualReferenced işlemi

Ad alanı: [Microsoft. hisse. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


İki işlem söz konusu olduğunda, tüm giriş durumları için aynı hareket ettikleri onaylar.

Bu onaylama işlemi, iki entanlı kasada bir qubit durum onaylamanın bir listesini azaltmak için Choi – Jamiołkowski isomorphism kullanılarak uygulanır.
Bu nedenle, bu işlem yalnızca sınanan her bir işlem için tek bir çağrıya gerek duyar, ancak ayrılacak sayıda qubit için iki kez gerekir.
Bu onaylama, örneğin, bir işlemin en iyi duruma getirilmiş bir sürümünün Naïve uygulamasına benzer bir şekilde davranması veya bir dizi hisse kullanım dışı girişleri üzerinde davranan bir işlemin bilinen durumları kabul ettiği bir işlem olduğundan emin olmak için kullanılabilir.

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Giriş

### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

Her bir işleme geçirilecek qubit sayısı.


### <a name="actual--qubit--unit"></a>gerçek: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) 

Test edilecek işlem.


### <a name="expected--qubit--unit--is-adj"></a>beklenen: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birimi](xref:microsoft.quantum.lang-ref.unit)  sıfatı

Test edilen işlem için beklenen davranışı tanımlayan işlem.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Açıklamalar

Bu işlem, yalnızca hedef kayıt üzerinde ters işlem yapılabilmesi için beklenen davranışı modelleyen işlemin adjointable olmasını gerektirir.
Tek bir tane, bu gereksinimi veren bir yeniden çevir işlemi belirtebilir, ancak devrik işlem, isteğe bağlı olarak rastgele bir işlem için genel olarak gerçekçi değildir ve bu nedenle bir seçenek olarak burada bulunmaz.