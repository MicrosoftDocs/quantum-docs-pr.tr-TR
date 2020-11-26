---
uid: Microsoft.Quantum.Math._ExtendedGreatestCommonDivisorI
title: _ExtendedGreatestCommonDivisorI işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: _ExtendedGreatestCommonDivisorI
qsharp.summary: Internal recursive call to calculate the GCD.
ms.openlocfilehash: b9acb21d57053b374c3a1831a81820ffc2a78ebb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211483"
---
# <a name="_extendedgreatestcommondivisori-function"></a><span data-ttu-id="a55aa-102">_ExtendedGreatestCommonDivisorI işlevi</span><span class="sxs-lookup"><span data-stu-id="a55aa-102">_ExtendedGreatestCommonDivisorI function</span></span>

<span data-ttu-id="a55aa-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a55aa-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a55aa-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a55aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a55aa-105">GCD 'yi hesaplamak için iç özyinelemeli çağrı.</span><span class="sxs-lookup"><span data-stu-id="a55aa-105">Internal recursive call to calculate the GCD.</span></span>

```qsharp
function _ExtendedGreatestCommonDivisorI (signA : Int, signB : Int, r : (Int, Int), s : (Int, Int), t : (Int, Int)) : (Int, Int)
```


## <a name="input"></a><span data-ttu-id="a55aa-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="a55aa-106">Input</span></span>

### <a name="signa--int"></a><span data-ttu-id="a55aa-107">signA: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a55aa-107">signA : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="signb--int"></a><span data-ttu-id="a55aa-108">signB: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a55aa-108">signB : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="r--intint"></a><span data-ttu-id="a55aa-109">r: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="a55aa-109">r : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="s--intint"></a><span data-ttu-id="a55aa-110">s: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="a55aa-110">s : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="t--intint"></a><span data-ttu-id="a55aa-111">t: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="a55aa-111">t : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>





## <a name="output--intint"></a><span data-ttu-id="a55aa-112">Çıkış: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="a55aa-112">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

