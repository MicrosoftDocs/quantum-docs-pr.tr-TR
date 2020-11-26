---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: e804e6a6ed82f14dcc9b8f721ad503d77922dc0f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194092"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="98630-102">LocalUnivariateMinimum işlevi</span><span class="sxs-lookup"><span data-stu-id="98630-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="98630-103">Ad alanı: [Microsoft. hisse. iyileştirmesi](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="98630-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="98630-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98630-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98630-105">Bir tek değişkenli işlev için, altın Aralık araması kullanarak, bir ayırt eden değer için yerel minimum değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="98630-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="98630-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="98630-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="98630-107">FN: [çift](xref:microsoft.quantum.lang-ref.double) -> [çift](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="98630-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="98630-108">Tek bir işlevin simge durumuna küçültülmesini sağlar.</span><span class="sxs-lookup"><span data-stu-id="98630-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="98630-109">sınırlar: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="98630-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="98630-110">Yerel minimumın bulunduğu Aralık.</span><span class="sxs-lookup"><span data-stu-id="98630-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="98630-111">Tolerans: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="98630-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="98630-112">İşlev girişi toleranslı olarak kullanılacak doğruluk.</span><span class="sxs-lookup"><span data-stu-id="98630-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="98630-113">Yerel opzma araması, aralığın genişliği bu toleranstan daha küçük olana kadar devam edecektir.</span><span class="sxs-lookup"><span data-stu-id="98630-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="98630-114">Çıkış: [Univariateoptimizationresult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="98630-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="98630-115">Verilen sınırlar içinde bulunan, belirtilen işlevin yerel bir optimizasyonu.</span><span class="sxs-lookup"><span data-stu-id="98630-115">A local optima of the given function, located within the given bounds.</span></span>