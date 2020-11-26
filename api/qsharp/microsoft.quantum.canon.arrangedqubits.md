---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217076"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="e4642-102">ArrangedQubits işlevi</span><span class="sxs-lookup"><span data-stu-id="e4642-102">ArrangedQubits function</span></span>

<span data-ttu-id="e4642-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e4642-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e4642-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e4642-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e4642-105">Bir dizine göre denetim, hedef ve yardımcı qubits 'i düzenleme</span><span class="sxs-lookup"><span data-stu-id="e4642-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="e4642-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e4642-106">Description</span></span>

<span data-ttu-id="e4642-107">0 dizininde target olan bir qubit dizisi, dizin 2 ^ i 'de ise denetim ı döndürür.</span><span class="sxs-lookup"><span data-stu-id="e4642-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="e4642-108">Yardımcı qugeler dizideki diğer tüm konumlara eklenir.</span><span class="sxs-lookup"><span data-stu-id="e4642-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="e4642-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="e4642-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="e4642-110">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4642-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="e4642-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e4642-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="e4642-112">yardımcı: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4642-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="e4642-113">Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e4642-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

