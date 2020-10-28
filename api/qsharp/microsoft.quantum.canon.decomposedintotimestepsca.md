---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728772"
---
# <a name="decomposedintotimestepsca-function"></a>DecomposedIntoTimeStepsCA işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Leyebilir [](https://nuget.org/packages/)


Belirli bir işlem için Trour – Suzuki tümleştirici uygulayan bir işlem döndürür.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="nsteps--int"></a>nSteps: [Int](xref:microsoft.quantum.lang-ref.int)

Zaman adımlarında kaldırılacak işlem sayısı.


### <a name="op--intdoublet--unit-adj--ctl"></a>Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL

Ayrıştırma için bir dizin girişi (türü `Int` ) ve bir zaman girişi (türü) kabul eden bir işlem `Double` .


### <a name="trotterorder--int"></a>Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)

Kullanılacak Trour – Suzuki tümleştirici sırasını seçer.
Sipariş 1 ve hatta 2, 4, 6,... Şu anda destekleniyor.



## <a name="output--doublet--unit-adj--ctl"></a>Çıkış: ([çift](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit) ayarlama ve CTL

İlk parametrenin `Double` tümleştirme adımı boyutu olduğu ve ikinci parametrenin üzerinde işlem yapılma hedefi olan Trour – Suzuki tümleştirmesini uygulayan bir Unitary döndürür.

## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

Her zaman adımının üzerinde işlem yapması gereken tür; Genellikle, `Qubit[]` ya da `Qubit` .

## <a name="remarks"></a>Açıklamalar

`order`Şuna eşit ile çağrıldığında `1` , bu işlev en düşük sıralı Baur – Suzuki tümleştirici $ $ \begin{hizalaması} s_1 (\lambda) = \ Prod_ {j = 1} ^ {m} e ^ {H_j \lambda} tarafından benzetilen bir işlem döndürür. \end{hizalaması} $ $ burada [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) ve Let $ \lambda $ 'ın bir evtime olması (döndürülen işlemin ilk girişi ile temsil edilir) ve izin ver $ \{ H_j \} _ {j = 1} ^ {m} $, " `op(j, lambda, _)` ^ {H_j \lambda} $ $e Unitary işleci tarafından benzetilen şekilde tümleştirildiği (skew-hermitian) dinamik.

Benzer şekilde, bir, `order` `2` ikinci sıra simetrik Trour – Suzuki tümleştirici $ $ \begin{hizalaması} S_2 (\lambda) = \ Prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ Prod_ {j ' = m} ^ {1} e ^ {h_ {j '} \lambda/2} döndürür.
\end{hizalaması} $ $

Daha yüksek değerler bile, `order` [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139)özyinelemeli yapımı kullanılarak uygulanır.

## <a name="references"></a>Referanslar

- [*D. W. Braz, G. Ahokas, R. Cleve, B. C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)