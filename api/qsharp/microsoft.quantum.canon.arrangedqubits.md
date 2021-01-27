---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841068"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="0bd02-102">ArrangedQubits işlevi</span><span class="sxs-lookup"><span data-stu-id="0bd02-102">ArrangedQubits function</span></span>

<span data-ttu-id="0bd02-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0bd02-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0bd02-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0bd02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0bd02-105">Bir dizine göre denetim, hedef ve yardımcı qubits 'i düzenleme</span><span class="sxs-lookup"><span data-stu-id="0bd02-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="0bd02-106">Description</span><span class="sxs-lookup"><span data-stu-id="0bd02-106">Description</span></span>

<span data-ttu-id="0bd02-107">0 dizininde target olan bir qubit dizisi, dizin 2 ^ i 'de ise denetim ı döndürür.</span><span class="sxs-lookup"><span data-stu-id="0bd02-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="0bd02-108">Yardımcı qugeler dizideki diğer tüm konumlara eklenir.</span><span class="sxs-lookup"><span data-stu-id="0bd02-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="0bd02-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="0bd02-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="0bd02-110">denetimler: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0bd02-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="0bd02-111">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0bd02-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="0bd02-112">yardımcı: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0bd02-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="0bd02-113">Çıkış: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0bd02-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

