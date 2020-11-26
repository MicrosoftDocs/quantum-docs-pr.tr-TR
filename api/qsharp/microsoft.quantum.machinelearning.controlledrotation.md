---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation Kullanıcı tanımlı tür
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196574"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation Kullanıcı tanımlı tür

Ad alanı: [Microsoft. hisse. Machinöğrenim](xref:Microsoft.Quantum.MachineLearning)

Paket: [Microsoft. hisse. Machine-öğrenim](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


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