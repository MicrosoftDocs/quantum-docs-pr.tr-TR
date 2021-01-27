---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848210"
---
# <a name="squarednorm-function"></a><span data-ttu-id="a04da-102">SquaredNorm işlevi</span><span class="sxs-lookup"><span data-stu-id="a04da-102">SquaredNorm function</span></span>

<span data-ttu-id="a04da-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a04da-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a04da-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a04da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a04da-105">Bir vektörün kare 2-normini döndürür.</span><span class="sxs-lookup"><span data-stu-id="a04da-105">Returns the squared 2-norm of a vector.</span></span>

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a><span data-ttu-id="a04da-106">Description</span><span class="sxs-lookup"><span data-stu-id="a04da-106">Description</span></span>

<span data-ttu-id="a04da-107">Bir vektörün kare 2-norm değerini döndürür; Yani, $ \vec{x} $ girişi verildiğinde $ \ sum_i x_i ^ 2 $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="a04da-107">Returns the squared 2-norm of a vector; that is, given an input $\vec{x}$, returns $\sum_i x_i^2$.</span></span>

## <a name="input"></a><span data-ttu-id="a04da-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="a04da-108">Input</span></span>

### <a name="array--double"></a><span data-ttu-id="a04da-109">dizi: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a04da-109">array : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a04da-110">Kare 2-norm döndürülmek üzere olan vektör.</span><span class="sxs-lookup"><span data-stu-id="a04da-110">The vector whose squared 2-norm is to be returned.</span></span>



## <a name="output--double"></a><span data-ttu-id="a04da-111">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a04da-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a04da-112">Kare 2-norm `array` .</span><span class="sxs-lookup"><span data-stu-id="a04da-112">The squared 2-norm of `array`.</span></span>