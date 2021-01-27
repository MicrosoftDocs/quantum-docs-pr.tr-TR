---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 33049b09405529bd418ff8652b6cb0f11bf734f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849063"
---
# <a name="notequalc-function"></a><span data-ttu-id="7c72b-102">NotEqualC işlevi</span><span class="sxs-lookup"><span data-stu-id="7c72b-102">NotEqualC function</span></span>

<span data-ttu-id="7c72b-103">Ad alanı: [Microsoft. hisse. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7c72b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7c72b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c72b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c72b-105">Yalnızca iki giriş eşitse true değerini döndürür.</span><span class="sxs-lookup"><span data-stu-id="7c72b-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="7c72b-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="7c72b-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="7c72b-107">y: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="7c72b-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="7c72b-108">Karşılaştırılacak ilk değer.</span><span class="sxs-lookup"><span data-stu-id="7c72b-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="7c72b-109">b: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="7c72b-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="7c72b-110">Karşılaştırılacak ikinci değer.</span><span class="sxs-lookup"><span data-stu-id="7c72b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7c72b-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7c72b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7c72b-112">`true` ve yalnızca `a` değerine eşit değilse `b` .</span><span class="sxs-lookup"><span data-stu-id="7c72b-112">`true` if and only if `a` is not equal to `b`.</span></span>