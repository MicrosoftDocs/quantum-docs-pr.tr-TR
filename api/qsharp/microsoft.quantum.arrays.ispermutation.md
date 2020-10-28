---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermütasyon işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730175"
---
# <a name="ispermutation-function"></a><span data-ttu-id="ebe2d-102">Ispermütasyon işlevi</span><span class="sxs-lookup"><span data-stu-id="ebe2d-102">IsPermutation function</span></span>

<span data-ttu-id="ebe2d-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ebe2d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ebe2d-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ebe2d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ebe2d-105">Yalnızca belirli bir dizi bir permütasyon temsil ediyorsa, true verir.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="ebe2d-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="ebe2d-106">Description</span></span>

<span data-ttu-id="ebe2d-107">Bir dizi `array` uzunluk verildiğinde `n` , ve yalnızca her bir tamsayı ' `0` `n - 1` de tam olarak bir kez görünüyorsa true, ancak `array` `array` öğeler üzerinde bir permütasyon olarak yorumlanabilecek şekilde döndürür `n` .</span><span class="sxs-lookup"><span data-stu-id="ebe2d-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="ebe2d-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="ebe2d-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="ebe2d-109">permütasyon: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ebe2d-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ebe2d-110">Bir permütasyon temsil eden veya temsil eden bir dizi.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ebe2d-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ebe2d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="ebe2d-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="ebe2d-112">Remarks</span></span>

<span data-ttu-id="ebe2d-113">Sıfır uzunluklu bir dizi, önemli ölçüde bir permütasyon.</span><span class="sxs-lookup"><span data-stu-id="ebe2d-113">An array of length zero is trivially a permutation.</span></span>