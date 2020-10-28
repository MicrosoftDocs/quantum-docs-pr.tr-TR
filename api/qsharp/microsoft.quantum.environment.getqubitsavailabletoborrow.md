---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Getqubitsavailabletoödünç alma işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727164"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Getqubitsavailabletoödünç alma işlemi

Ad alanı: [Microsoft. hisse. Environment](xref:Microsoft.Quantum.Environment)

Leyebilir [](https://nuget.org/packages/)


Şu anda ödünç alma için kullanılabilen qubits sayısını döndürür.
Buna kullanılmayan qubits dahildir; diğer bir deyişle, tarafından döndürülen qubits 'i de içerir `GetQubitsAvailableToUse` .

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)

Bir bildirimde ayrılabilen qubit sayısı `borrowing` .
Kullanılan hedef makine bu bilgileri sağlamıyorsa, `-1` döndürülür.

## <a name="see-also"></a>Ayrıca Bkz.

- [Microsoft. hisse. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)