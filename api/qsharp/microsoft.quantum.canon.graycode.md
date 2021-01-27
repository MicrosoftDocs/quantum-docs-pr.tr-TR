---
uid: Microsoft.Quantum.Canon.GrayCode
title: Gricode işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840490"
---
# <a name="graycode-function"></a><span data-ttu-id="e8385-102">Gricode işlevi</span><span class="sxs-lookup"><span data-stu-id="e8385-102">GrayCode function</span></span>

<span data-ttu-id="e8385-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e8385-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e8385-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8385-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8385-105">Gri kod sıraları oluşturur</span><span class="sxs-lookup"><span data-stu-id="e8385-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="e8385-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="e8385-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="e8385-107">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8385-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8385-108">Bit sayısı</span><span class="sxs-lookup"><span data-stu-id="e8385-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="e8385-109">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="e8385-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="e8385-110">Tanımlama grubu dizisi.</span><span class="sxs-lookup"><span data-stu-id="e8385-110">Array of tuples.</span></span> <span data-ttu-id="e8385-111">Kayıt alanındaki ilk değer, bir sonraki bir değere ulaşmak için geçerli değerde değişmek üzere, kayıt düzeni içindeki Ikinci değer olan gride bir değerdir.</span><span class="sxs-lookup"><span data-stu-id="e8385-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>

## <a name="example"></a><span data-ttu-id="e8385-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="e8385-112">Example</span></span>

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```