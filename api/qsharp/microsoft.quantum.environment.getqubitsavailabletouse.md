---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727163"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="656a7-102">GetQubitsAvailableToUse işlemi</span><span class="sxs-lookup"><span data-stu-id="656a7-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="656a7-103">Ad alanı: [Microsoft. hisse. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="656a7-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="656a7-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="656a7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="656a7-105">Şu anda kullanılabilecek qubits sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="656a7-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="656a7-106">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="656a7-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="656a7-107">Bir bildirimde ayrılabilen qubit sayısı `using` .</span><span class="sxs-lookup"><span data-stu-id="656a7-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="656a7-108">Kullanılan hedef makine bu bilgileri sağlamıyorsa, `-1` döndürülür.</span><span class="sxs-lookup"><span data-stu-id="656a7-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="656a7-109">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="656a7-109">See Also</span></span>

- [<span data-ttu-id="656a7-110">Microsoft. hisse. Environment. Getqubitsavailabletoödünç alma</span><span class="sxs-lookup"><span data-stu-id="656a7-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)