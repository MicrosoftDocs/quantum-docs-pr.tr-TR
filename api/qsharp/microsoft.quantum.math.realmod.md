---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731039"
---
# <a name="realmod-function"></a><span data-ttu-id="b3973-102">RealMod işlevi</span><span class="sxs-lookup"><span data-stu-id="b3973-102">RealMod function</span></span>

<span data-ttu-id="b3973-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b3973-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b3973-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3973-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3973-105">İki gerçek sayı arasındaki mod sayısını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="b3973-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="b3973-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="b3973-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="b3973-107">değer: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b3973-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b3973-108">' Nin mod ' A kadar olan gerçek bir sayı $x.</span><span class="sxs-lookup"><span data-stu-id="b3973-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="b3973-109">Modül: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b3973-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b3973-110">$X $ ' in ' i ' ile karşılaştırıldığında, gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="b3973-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="b3973-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b3973-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b3973-112">Bu işlev tarafından döndürülecek en küçük değer.</span><span class="sxs-lookup"><span data-stu-id="b3973-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="b3973-113">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b3973-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="b3973-114">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="b3973-114">Remarks</span></span>

<span data-ttu-id="b3973-115">Bu işlev, birim çemberi gerçek satırı kaydırarak gerçek mod 'u hesaplar ve ardından girişe karşılık gelen birim çemberde açısını buluyor.</span><span class="sxs-lookup"><span data-stu-id="b3973-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="b3973-116">`minValue`Daha sonra giriş, birim çemberin nerede kesilip kesilbir şekilde belirtir.</span><span class="sxs-lookup"><span data-stu-id="b3973-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>