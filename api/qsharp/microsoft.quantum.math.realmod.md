---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848358"
---
# <a name="realmod-function"></a><span data-ttu-id="aaea9-102">RealMod işlevi</span><span class="sxs-lookup"><span data-stu-id="aaea9-102">RealMod function</span></span>

<span data-ttu-id="aaea9-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="aaea9-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="aaea9-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aaea9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aaea9-105">İki gerçek sayı arasındaki mod sayısını hesaplar.</span><span class="sxs-lookup"><span data-stu-id="aaea9-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="aaea9-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="aaea9-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="aaea9-107">değer: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aaea9-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aaea9-108">' Nin mod ' A kadar olan gerçek bir sayı $x.</span><span class="sxs-lookup"><span data-stu-id="aaea9-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="aaea9-109">Modül: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aaea9-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aaea9-110">$X $ ' in ' i ' ile karşılaştırıldığında, gerçek sayı.</span><span class="sxs-lookup"><span data-stu-id="aaea9-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="aaea9-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aaea9-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aaea9-112">Bu işlev tarafından döndürülecek en küçük değer.</span><span class="sxs-lookup"><span data-stu-id="aaea9-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="aaea9-113">Çıkış: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aaea9-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="aaea9-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="aaea9-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="aaea9-115">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="aaea9-115">Remarks</span></span>

<span data-ttu-id="aaea9-116">Bu işlev, birim çemberi gerçek satırı kaydırarak gerçek mod 'u hesaplar ve ardından girişe karşılık gelen birim çemberde açısını buluyor.</span><span class="sxs-lookup"><span data-stu-id="aaea9-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="aaea9-117">`minValue`Daha sonra giriş, birim çemberin nerede kesilip kesilbir şekilde belirtir.</span><span class="sxs-lookup"><span data-stu-id="aaea9-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>