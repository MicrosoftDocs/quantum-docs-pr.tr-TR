---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728333"
---
# <a name="trotter2implca-operation"></a>Trotter2ImplCA işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


İkinci sipariş rahatlığını – Suzuki tümleştirici uygulama.

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a>Giriş

### <a name="nsteps--int"></a>nSteps: [Int](xref:microsoft.quantum.lang-ref.int)

Zaman adımlarında kaldırılacak işlem sayısı.


### <a name="op--intdoublet--unit-adj--ctl"></a>Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL

Bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü `Double` ) ve ayrıştırma için bir hisse kayıt (tür) kabul eden bir işlem `'T` .


### <a name="stepsize--double"></a>stepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Simülasyonun her adımının boyut çarpanı.


### <a name="target--t"></a>Hedef: 'T

İşlemlerin davranabileceği bir hisse kayıt.



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .