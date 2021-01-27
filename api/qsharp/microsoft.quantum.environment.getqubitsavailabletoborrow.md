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
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="69377-102">Getqubitsavailabletoödünç alma işlemi</span><span class="sxs-lookup"><span data-stu-id="69377-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="69377-103">Ad alanı: [Microsoft. hisse. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="69377-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="69377-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="69377-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="69377-105">Şu anda ödünç alma için kullanılabilen qubits sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="69377-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="69377-106">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69377-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69377-107">Ödünç alınan ve bir deyimin parçası olarak ayrılabilen qubit sayısı `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="69377-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="69377-108">Kullanılan hedef makine bu bilgileri sağlamıyorsa, `-1` döndürülür.</span><span class="sxs-lookup"><span data-stu-id="69377-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="69377-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="69377-109">See Also</span></span>

- [<span data-ttu-id="69377-110">Microsoft. hisse. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="69377-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)