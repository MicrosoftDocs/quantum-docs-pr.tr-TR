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
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="5d11b-102">Getqubitsavailabletoödünç alma işlemi</span><span class="sxs-lookup"><span data-stu-id="5d11b-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="5d11b-103">Ad alanı: [Microsoft. hisse. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="5d11b-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="5d11b-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5d11b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5d11b-105">Şu anda ödünç alma için kullanılabilen qubits sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="5d11b-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="5d11b-106">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d11b-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d11b-107">Ödünç alınan ve bir deyimin parçası olarak ayrılabilen qubit sayısı `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="5d11b-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="5d11b-108">Kullanılan hedef makine bu bilgileri sağlamıyorsa, `-1` döndürülür.</span><span class="sxs-lookup"><span data-stu-id="5d11b-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d11b-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5d11b-109">See Also</span></span>

- [<span data-ttu-id="5d11b-110">Microsoft. hisse. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="5d11b-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)