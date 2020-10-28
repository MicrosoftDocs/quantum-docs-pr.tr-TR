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
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="00e3c-102">Getqubitsavailabletoödünç alma işlemi</span><span class="sxs-lookup"><span data-stu-id="00e3c-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="00e3c-103">Ad alanı: [Microsoft. hisse. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="00e3c-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="00e3c-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00e3c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00e3c-105">Şu anda ödünç alma için kullanılabilen qubits sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="00e3c-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="00e3c-106">Buna kullanılmayan qubits dahildir; diğer bir deyişle, tarafından döndürülen qubits 'i de içerir `GetQubitsAvailableToUse` .</span><span class="sxs-lookup"><span data-stu-id="00e3c-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="00e3c-107">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="00e3c-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="00e3c-108">Bir bildirimde ayrılabilen qubit sayısı `borrowing` .</span><span class="sxs-lookup"><span data-stu-id="00e3c-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="00e3c-109">Kullanılan hedef makine bu bilgileri sağlamıyorsa, `-1` döndürülür.</span><span class="sxs-lookup"><span data-stu-id="00e3c-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="00e3c-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="00e3c-110">See Also</span></span>

- [<span data-ttu-id="00e3c-111">Microsoft. hisse. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="00e3c-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)