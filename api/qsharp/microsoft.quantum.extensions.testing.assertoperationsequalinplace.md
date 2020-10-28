---
uid: Microsoft.Quantum.Extensions.Testing.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Extensions.Testing
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  > [!WARNING]

  > AssertOperationsEqualInPlace has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> instead.

  >

  > Please use @"microsoft.quantum.diagnostics.assertoperationsequalinplace".

  > Note that the order of the arguments to this operation has changed.
ms.openlocfilehash: 6d2ead95a60ed3cc8ee95fb7f91e1aa49d366a48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726774"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace işlemi

Ad alanı: [Microsoft. hisse. Extensions. test](xref:Microsoft.Quantum.Extensions.Testing)

Leyebilir [](https://nuget.org/packages/)


> [!WARNING]
> AssertOperationsEqualInPlace kullanım dışı bırakıldı. Lütfen <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> bunun yerine kullanın.
>
> Lütfen @"microsoft.quantum.diagnostics.assertoperationsequalinplace" kullanın.
> Bu işlem için bağımsız değişkenlerin sırasının değiştiğini unutmayın.



```qsharp
operation AssertOperationsEqualInPlace (actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj), nQubits : Int) : Unit
```


## <a name="input"></a>Giriş

### <a name="actual--qubit--unit"></a>gerçek: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [birim](xref:microsoft.quantum.lang-ref.unit) 




### <a name="expected--qubit--unit-adj"></a>beklenen: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması




### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)

