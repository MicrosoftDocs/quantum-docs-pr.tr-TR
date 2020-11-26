---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201419"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="1fe22-102">GetQubitsAvailableToUse işlemi</span><span class="sxs-lookup"><span data-stu-id="1fe22-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="1fe22-103">Ad alanı: [Microsoft. hisse. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="1fe22-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="1fe22-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1fe22-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1fe22-105">Şu anda kullanılabilecek qubits sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="1fe22-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="1fe22-106">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1fe22-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1fe22-107">Bir bildirimde ayrılabilen qubit sayısı `using` .</span><span class="sxs-lookup"><span data-stu-id="1fe22-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="1fe22-108">Kullanılan hedef makine bu bilgileri sağlamıyorsa, `-1` döndürülür.</span><span class="sxs-lookup"><span data-stu-id="1fe22-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fe22-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1fe22-109">See Also</span></span>

- [<span data-ttu-id="1fe22-110">Microsoft. hisse. Environment. Getqubitsavailabletoödünç alma</span><span class="sxs-lookup"><span data-stu-id="1fe22-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)