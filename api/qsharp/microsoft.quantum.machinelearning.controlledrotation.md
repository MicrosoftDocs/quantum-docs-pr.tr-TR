---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation Kullanıcı tanımlı tür
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847403"
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

## <a name="example"></a>Örnek

Aşağıda, bir kayıttaki ilk qubitin $X $ ekseni ile ilgili bir döndürme ve ikinci qubit üzerinde denetlenen ve ardışık bir modeldeki dördüncü parametre tarafından verilen bir açı gösterilmektedir:

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>Açıklamalar

Denetlenmeyen bir döndürme `ControlIndices` , boş bir dizin dizisine ayarlanarak gösterilebilir `new Int[0]` .