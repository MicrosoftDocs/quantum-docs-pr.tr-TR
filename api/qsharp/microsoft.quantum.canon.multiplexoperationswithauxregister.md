---
uid: Microsoft.Quantum.Canon.MultiplexOperationsWithAuxRegister
title: Multiplexoperationswithlarregister işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsWithAuxRegister
qsharp.summary: Implementation step of MultiplexOperations.
ms.openlocfilehash: 91db22d6261709c1c3506c80ff600c904748575a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852471"
---
# <a name="multiplexoperationswithauxregister-operation"></a>Multiplexoperationswithlarregister işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Çoğullexoperations 'ın uygulama adımı.

```qsharp
operation MultiplexOperationsWithAuxRegister<'T> (unitaries : ('T => Unit is Adj + Ctl)[], auxillaryRegister : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Giriş

### <a name="unitaries--t--unit--is-adj--ctl"></a>birimlere göre: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  ayarlama ve CTL []




### <a name="auxillaryregister--qubit"></a>Gııllaryregister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="index--littleendian"></a>Dizin: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)




### <a name="target--t"></a>Hedef: 'T





## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Tür Parametreleri

### <a name="t"></a>Görüntülenemeyen



## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Canon. MultiplexOperations](xref:Microsoft.Quantum.Canon.MultiplexOperations)