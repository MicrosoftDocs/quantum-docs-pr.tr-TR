---
uid: Microsoft.Quantum.Canon.GrayCode
title: Gricode işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206893"
---
# <a name="graycode-function"></a><span data-ttu-id="9d1a0-102">Gricode işlevi</span><span class="sxs-lookup"><span data-stu-id="9d1a0-102">GrayCode function</span></span>

<span data-ttu-id="9d1a0-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9d1a0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9d1a0-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9d1a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9d1a0-105">Gri kod sıraları oluşturur</span><span class="sxs-lookup"><span data-stu-id="9d1a0-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="9d1a0-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="9d1a0-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="9d1a0-107">n: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9d1a0-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9d1a0-108">Bit sayısı</span><span class="sxs-lookup"><span data-stu-id="9d1a0-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="9d1a0-109">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="9d1a0-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="9d1a0-110">Tanımlama grubu dizisi.</span><span class="sxs-lookup"><span data-stu-id="9d1a0-110">Array of tuples.</span></span> <span data-ttu-id="9d1a0-111">Kayıt alanındaki ilk değer, bir sonraki bir değere ulaşmak için geçerli değerde değişmek üzere, kayıt düzeni içindeki Ikinci değer olan gride bir değerdir.</span><span class="sxs-lookup"><span data-stu-id="9d1a0-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>