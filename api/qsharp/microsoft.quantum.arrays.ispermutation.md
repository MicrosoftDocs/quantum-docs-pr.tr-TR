---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermütasyon işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220935"
---
# <a name="ispermutation-function"></a><span data-ttu-id="60234-102">Ispermütasyon işlevi</span><span class="sxs-lookup"><span data-stu-id="60234-102">IsPermutation function</span></span>

<span data-ttu-id="60234-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="60234-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="60234-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60234-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60234-105">Yalnızca belirli bir dizi bir permütasyon temsil ediyorsa, true verir.</span><span class="sxs-lookup"><span data-stu-id="60234-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="60234-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="60234-106">Description</span></span>

<span data-ttu-id="60234-107">Bir dizi `array` uzunluk verildiğinde `n` , ve yalnızca her bir tamsayı ' `0` `n - 1` de tam olarak bir kez görünüyorsa true, ancak `array` `array` öğeler üzerinde bir permütasyon olarak yorumlanabilecek şekilde döndürür `n` .</span><span class="sxs-lookup"><span data-stu-id="60234-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="60234-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="60234-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="60234-109">permütasyon: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="60234-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="60234-110">Bir permütasyon temsil eden veya temsil eden bir dizi.</span><span class="sxs-lookup"><span data-stu-id="60234-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="60234-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="60234-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="60234-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="60234-112">Remarks</span></span>

<span data-ttu-id="60234-113">Sıfır uzunluklu bir dizi, önemli ölçüde bir permütasyon.</span><span class="sxs-lookup"><span data-stu-id="60234-113">An array of length zero is trivially a permutation.</span></span>