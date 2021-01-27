---
uid: Microsoft.Quantum.Bitwise.Not
title: Not işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: Not
qsharp.summary: Returns the bitwise NOT of an integer. This performs the same computation as the built-in `~~~` operator.
ms.openlocfilehash: 9c7642770c4f1db4878ccc1aba288fb9254e017e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842109"
---
# <a name="not-function"></a><span data-ttu-id="5c5f9-102">Not işlevi</span><span class="sxs-lookup"><span data-stu-id="5c5f9-102">Not function</span></span>

<span data-ttu-id="5c5f9-103">Ad alanı: [Microsoft. hisse. bit düzeyinde](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="5c5f9-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="5c5f9-104">Paket: [Microsoft. hisse. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5c5f9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5c5f9-105">Bir tamsayı DEĞIL bit seviyesinde değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="5c5f9-105">Returns the bitwise NOT of an integer.</span></span>
<span data-ttu-id="5c5f9-106">Bu, yerleşik işleçle aynı hesaplamayı gerçekleştirir `~~~` .</span><span class="sxs-lookup"><span data-stu-id="5c5f9-106">This performs the same computation as the built-in `~~~` operator.</span></span>

```qsharp
function Not (a : Int) : Int
```


## <a name="input"></a><span data-ttu-id="5c5f9-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="5c5f9-107">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5c5f9-108">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c5f9-108">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="5c5f9-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c5f9-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="example"></a><span data-ttu-id="5c5f9-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="5c5f9-110">Example</span></span>

```qsharp
let a = 248;
let x = Not(a); // x : Int = -249, due to two's complement representation.
```

## <a name="remarks"></a><span data-ttu-id="5c5f9-111">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5c5f9-111">Remarks</span></span>

<span data-ttu-id="5c5f9-112">Daha fazla ayrıntı için bkz. [C# ~ işleci](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) .</span><span class="sxs-lookup"><span data-stu-id="5c5f9-112">See the [C# ~ Operator](https://docs.microsoft.com/dotnet/csharp/language-reference/operators/bitwise-complement-operator) for more details.</span></span>