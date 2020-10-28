---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation Kullanıcı tanımlı tür
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726641"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Leyebilir [](https://nuget.org/packages/)


Hedef ve denetim dizinleri, döndürme ekseni ve Dizin bir model parametresi vektörüne göre denetimli bir döndürmeyi açıklar.

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>Adlandırılmış öğeler

### <a name="targetindex--int"></a>Targetındex: [Int](xref:microsoft.quantum.lang-ref.int)

Bu denetimli döndürme için hedef qubit dizini.
### <a name="controlindices--int"></a>Controlindıces: [Int](xref:microsoft.quantum.lang-ref.int)[]

Bu döndürme için bir denetim qubit dizinleri dizisi.
### <a name="axis--pauli"></a>Eksen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Bu döndürme için eksen.
### <a name="parameterindex--int"></a>ParameterIndex: [Int](xref:microsoft.quantum.lang-ref.int)

Bu döndürme açısını açıklayan bir model parametresi vektörüne bir dizin.

## <a name="remarks"></a>Açıklamalar

Denetlenmeyen bir döndürme `ControlIndices` , boş bir dizin dizisine ayarlanarak gösterilebilir `new Int[0]` .