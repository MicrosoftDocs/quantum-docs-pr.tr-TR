---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Getqubitsavailabletoödünç alma işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201470"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Getqubitsavailabletoödünç alma işlemi

Ad alanı: [Microsoft. hisse. Environment](xref:Microsoft.Quantum.Environment)

Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Şu anda ödünç alma için kullanılabilen qubits sayısını döndürür.

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Ödünç alınan ve bir deyimin parçası olarak ayrılabilen qubit sayısı `borrowing` .
Kullanılan hedef makine bu bilgileri sağlamıyorsa, `-1` döndürülür.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)