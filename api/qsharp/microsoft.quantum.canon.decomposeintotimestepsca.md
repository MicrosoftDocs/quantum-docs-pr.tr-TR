---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: aa004098cbc805126109d3356f0f6550b85cd60b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840727"
---
# <a name="decomposeintotimestepsca-function"></a>DecomposeIntoTimeStepsCA işlevi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> DecomposeIntoTimeStepsCA kullanım dışı bırakıldı. Lütfen <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> bunun yerine kullanın.



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Giriş

### <a name="nsteps--int"></a>nSteps: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--intdoublet--unit--is-adj--ctl"></a>Op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [birimi](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL




### <a name="trotterorder--int"></a>Trokorder: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--doublet--unit--is-adj--ctl"></a>Çıkış: ([çift](xref:microsoft.quantum.lang-ref.double), 't) => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen

