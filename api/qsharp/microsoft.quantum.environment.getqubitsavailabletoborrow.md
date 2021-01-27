---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Getqubitsavailabletoödünç alma işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853241"
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