---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Permütasyon Tequbits işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205617"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="a8f4c-102">Permütasyon Tequbits işlemi</span><span class="sxs-lookup"><span data-stu-id="a8f4c-102">PermuteQubits operation</span></span>

<span data-ttu-id="a8f4c-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8f4c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8f4c-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8f4c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8f4c-105">DEĞIŞTIRME işlemini kullanarak permütasyon qutes.</span><span class="sxs-lookup"><span data-stu-id="a8f4c-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a8f4c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a8f4c-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="a8f4c-107">sıralama: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a8f4c-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a8f4c-108">Qubits 'in, bu dizindeki qubit 'in Şu anda [i] sıralamada olacağı yeni sıralamasını açıklar.</span><span class="sxs-lookup"><span data-stu-id="a8f4c-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="a8f4c-109">kaydol: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a8f4c-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a8f4c-110">Üzerinde işlem yapmak için qubit kaydolun.</span><span class="sxs-lookup"><span data-stu-id="a8f4c-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8f4c-111">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8f4c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

