---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermütasyon işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848087"
---
# <a name="ispermutation-function"></a><span data-ttu-id="39d42-102">Ispermütasyon işlevi</span><span class="sxs-lookup"><span data-stu-id="39d42-102">IsPermutation function</span></span>

<span data-ttu-id="39d42-103">Ad alanı: [Microsoft. hisse. dizileri](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="39d42-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="39d42-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39d42-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39d42-105">Yalnızca belirli bir dizi bir permütasyon temsil ediyorsa, true verir.</span><span class="sxs-lookup"><span data-stu-id="39d42-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="39d42-106">Description</span><span class="sxs-lookup"><span data-stu-id="39d42-106">Description</span></span>

<span data-ttu-id="39d42-107">Bir dizi `array` uzunluk verildiğinde `n` , ve yalnızca her bir tamsayı ' `0` `n - 1` de tam olarak bir kez görünüyorsa true, ancak `array` `array` öğeler üzerinde bir permütasyon olarak yorumlanabilecek şekilde döndürür `n` .</span><span class="sxs-lookup"><span data-stu-id="39d42-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="39d42-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="39d42-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="39d42-109">permütasyon: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="39d42-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="39d42-110">Bir permütasyon temsil eden veya temsil eden bir dizi.</span><span class="sxs-lookup"><span data-stu-id="39d42-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="39d42-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="39d42-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="39d42-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="39d42-112">Example</span></span>

<span data-ttu-id="39d42-113">Aşağıdaki Q # kodu "tüm Tanılamalar başarıyla tamamlandı" iletisini yazdırır:</span><span class="sxs-lookup"><span data-stu-id="39d42-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="39d42-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="39d42-114">Remarks</span></span>

<span data-ttu-id="39d42-115">Sıfır uzunluklu bir dizi, önemli ölçüde bir permütasyon.</span><span class="sxs-lookup"><span data-stu-id="39d42-115">An array of length zero is trivially a permutation.</span></span>