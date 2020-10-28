---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Permütasyon Tequbits işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728483"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="a8d18-102">Permütasyon Tequbits işlemi</span><span class="sxs-lookup"><span data-stu-id="a8d18-102">PermuteQubits operation</span></span>

<span data-ttu-id="a8d18-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8d18-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8d18-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8d18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8d18-105">DEĞIŞTIRME işlemini kullanarak permütasyon qutes.</span><span class="sxs-lookup"><span data-stu-id="a8d18-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a8d18-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a8d18-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="a8d18-107">sıralama: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a8d18-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a8d18-108">Qubits 'in, bu dizindeki qubit 'in Şu anda [i] sıralamada olacağı yeni sıralamasını açıklar.</span><span class="sxs-lookup"><span data-stu-id="a8d18-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="a8d18-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a8d18-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a8d18-110">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="a8d18-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8d18-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8d18-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

