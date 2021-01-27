---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 34b60934b67c19b2d1d718d68b85a2f0fffeab5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852029"
---
# <a name="trotter2implca-operation"></a>Trotter2ImplCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


İkinci sipariş rahatlığını – Suzuki tümleştirici uygulama.

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="nsteps--int"></a>nSteps: [Int](xref:microsoft.quantum.lang-ref.int)

Zaman adımlarında kaldırılacak işlem sayısı.


### <a name="op--intdoublet--unit--is-adj--ctl"></a>Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL

Bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü `Double` ) ve ayrıştırma için bir hisse kayıt (tür) kabul eden bir işlem `'T` .


### <a name="stepsize--double"></a>stepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Simülasyonun her adımının boyut çarpanı.


### <a name="target--t"></a>Hedef: 'T

İşlemlerin davranabileceği bir hisse kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .

## <a name="example"></a>Örnek

Aşağıdakiler eşdeğerdir:

```qsharp
op(0, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(0, deltaT / 2.0, target);
```

ve

```qsharp
Trotter2ImplCA((2, op), deltaT, target);
```