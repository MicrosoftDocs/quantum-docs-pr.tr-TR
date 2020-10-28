---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f5cce3429b72f0ff6e00c2079241272881512da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728946"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="e2463-102">ArrangedQubits işlevi</span><span class="sxs-lookup"><span data-stu-id="e2463-102">ArrangedQubits function</span></span>

<span data-ttu-id="e2463-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e2463-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e2463-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2463-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2463-105">Bir dizine göre denetim, hedef ve yardımcı qubits 'i düzenleme</span><span class="sxs-lookup"><span data-stu-id="e2463-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="e2463-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="e2463-106">Description</span></span>

<span data-ttu-id="e2463-107">0 dizininde target olan bir qubit dizisi, dizin 2 ^ i 'de ise denetim ı döndürür.</span><span class="sxs-lookup"><span data-stu-id="e2463-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="e2463-108">Yardımcı qugeler dizideki diğer tüm konumlara eklenir.</span><span class="sxs-lookup"><span data-stu-id="e2463-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="e2463-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="e2463-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="e2463-110">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e2463-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="e2463-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e2463-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="e2463-112">yardımcı: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e2463-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="e2463-113">Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e2463-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

