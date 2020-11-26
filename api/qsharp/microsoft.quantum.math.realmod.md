---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228262"
---
# <a name="realmod-function"></a><span data-ttu-id="88ddc-102">RealMod işlevi</span><span class="sxs-lookup"><span data-stu-id="88ddc-102">RealMod function</span></span>

<span data-ttu-id="88ddc-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="88ddc-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="88ddc-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88ddc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88ddc-105">İki gerçek sayı arasındaki mod sayısını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="88ddc-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="88ddc-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="88ddc-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="88ddc-107">değer: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88ddc-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88ddc-108">' Nin mod ' A kadar olan gerçek bir sayı $x.</span><span class="sxs-lookup"><span data-stu-id="88ddc-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="88ddc-109">Modül: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88ddc-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88ddc-110">$X $ ' in ' i ' ile karşılaştırıldığında, gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="88ddc-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="88ddc-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88ddc-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88ddc-112">Bu işlev tarafından döndürülecek en küçük değer.</span><span class="sxs-lookup"><span data-stu-id="88ddc-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="88ddc-113">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88ddc-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="88ddc-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="88ddc-114">Remarks</span></span>

<span data-ttu-id="88ddc-115">Bu işlev, birim çemberi gerçek satırı kaydırarak gerçek mod 'u hesaplar ve ardından girişe karşılık gelen birim çemberde açısını buluyor.</span><span class="sxs-lookup"><span data-stu-id="88ddc-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="88ddc-116">`minValue`Daha sonra giriş, birim çemberin nerede kesilip kesilbir şekilde belirtir.</span><span class="sxs-lookup"><span data-stu-id="88ddc-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>