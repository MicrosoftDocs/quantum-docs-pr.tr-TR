---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848556"
---
# <a name="headandrest-function"></a><span data-ttu-id="9eb27-102">HeadAndRest işlevi</span><span class="sxs-lookup"><span data-stu-id="9eb27-102">HeadAndRest function</span></span>

<span data-ttu-id="9eb27-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9eb27-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9eb27-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9eb27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9eb27-105">Dizinin ilk ve kalan öğelerinin bir listesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="9eb27-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="9eb27-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9eb27-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="9eb27-107">dizi: ' A []</span><span class="sxs-lookup"><span data-stu-id="9eb27-107">array : 'A[]</span></span>

<span data-ttu-id="9eb27-108">En az bir öğesi olan bir dizi.</span><span class="sxs-lookup"><span data-stu-id="9eb27-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="9eb27-109">Çıkış: (' A, ' A [])</span><span class="sxs-lookup"><span data-stu-id="9eb27-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="9eb27-110">Dizinin ilk ve kalan öğelerinin bir başlığı.</span><span class="sxs-lookup"><span data-stu-id="9eb27-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9eb27-111">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="9eb27-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="9eb27-112">' A</span><span class="sxs-lookup"><span data-stu-id="9eb27-112">'A</span></span>

<span data-ttu-id="9eb27-113">Dizi öğelerinin türü.</span><span class="sxs-lookup"><span data-stu-id="9eb27-113">The type of the array elements.</span></span>