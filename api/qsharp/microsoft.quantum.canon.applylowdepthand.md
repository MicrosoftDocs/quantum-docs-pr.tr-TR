---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 4c5e381227bf82415121add38d0c0d2959fb529d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209324"
---
# <a name="applylowdepthand-operation"></a>ApplyLowDepthAnd işlemi

Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)


Yalnızca her iki denetim qubit de 1 durumda ise, adeklem işlemini gerçekleştirmek için ölçümü kullanarak, belirli bir hedef QUI 'yi tersine çevirir.

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Açıklama

`target`Ve yalnızca her iki denetim 1 ise, ancak 0 durumunda olduğunu varsaymaktadır `target` .  İşlem T-Count 4, T-Depth 1 ve bir yardımcı qubit gerektirir ve bu nedenle, 0 olarak bilindiğinde CCNOT işlemi tercih edilebilir `target` .  Bu işlemin adekçine ölçüm tabanlıdır ve hiçbir T kapısı gerektirmez ve yardımcı qubit yoktur.

## <a name="input"></a>Giriş

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İlk denetim qubit


### <a name="control2--qubit"></a>Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

İkinci denetim qubit


### <a name="target--qubit"></a>Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Hedef yardımcı qubit; 0 durumunda olmalıdır



## <a name="output--unit"></a>Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Başvurular

- Cody Jones: "hata toleranslı Toffoli kapısı için önemli kurulumlarını", fiziksel. Rev. A 87, 022328, 2013 [Arxıv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328
- Peter Selger: "hisse başına T-derinlik bir", fiziksel. Rev. A 87, 042302, 2013 [Arxıv: 1210.0974](https://arxiv.org/abs/1210.0974) doi: 10.1103/PhysRevA. 87.042302