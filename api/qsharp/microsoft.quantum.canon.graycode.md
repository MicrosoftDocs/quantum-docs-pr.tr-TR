---
uid: Microsoft.Quantum.Canon.GrayCode
title: Gricode işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728699"
---
# <a name="graycode-function"></a><span data-ttu-id="5113f-102">Gricode işlevi</span><span class="sxs-lookup"><span data-stu-id="5113f-102">GrayCode function</span></span>

<span data-ttu-id="5113f-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5113f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5113f-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5113f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5113f-105">Gri kod sıraları oluşturur</span><span class="sxs-lookup"><span data-stu-id="5113f-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="5113f-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="5113f-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="5113f-107">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5113f-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5113f-108">Bit sayısı</span><span class="sxs-lookup"><span data-stu-id="5113f-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="5113f-109">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="5113f-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="5113f-110">Tanımlama grubu dizisi.</span><span class="sxs-lookup"><span data-stu-id="5113f-110">Array of tuples.</span></span> <span data-ttu-id="5113f-111">Kayıt alanındaki ilk değer, bir sonraki bir değere ulaşmak için geçerli değerde değişmek üzere, kayıt düzeni içindeki Ikinci değer olan gride bir değerdir.</span><span class="sxs-lookup"><span data-stu-id="5113f-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>