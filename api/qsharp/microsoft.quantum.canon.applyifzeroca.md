---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: ApplyIfZeroCA işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 85612bd3dd7af45b7901fef775a7d556eb229608
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729486"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="eb425-102">ApplyIfZeroCA işlemi</span><span class="sxs-lookup"><span data-stu-id="eb425-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="eb425-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb425-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb425-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb425-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb425-105">Klasik sonuç değeri sıfır olan bir Unitary işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="eb425-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="eb425-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="eb425-106">Description</span></span>

<span data-ttu-id="eb425-107">Bir işlem `op` ve sonuç değeri verildiğinde, `result` if ise `op` için geçerlidir `target` `result` `Zero` .</span><span class="sxs-lookup"><span data-stu-id="eb425-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="eb425-108">Varsa, `One` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="eb425-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="eb425-109">Sonek, `CA` uygulanacak işlemin Unitary (denetlenebilir ve adjointable) olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="eb425-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="eb425-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="eb425-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="eb425-111">Sonuç: __geçersiz <Result>__</span><span class="sxs-lookup"><span data-stu-id="eb425-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="eb425-112">Op 'ın uygulanıp uygulanmadığını denetleyen ölçüm sonucu.</span><span class="sxs-lookup"><span data-stu-id="eb425-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="eb425-113">Op: 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) ayarlaması + CTL</span><span class="sxs-lookup"><span data-stu-id="eb425-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="eb425-114">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="eb425-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="eb425-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="eb425-115">target : 'T</span></span>

<span data-ttu-id="eb425-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="eb425-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb425-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb425-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eb425-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="eb425-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb425-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="eb425-119">'T</span></span>

<span data-ttu-id="eb425-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="eb425-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb425-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="eb425-121">See Also</span></span>

- [<span data-ttu-id="eb425-122">Microsoft. hisse. Canon. Applyifsıfırlaması c</span><span class="sxs-lookup"><span data-stu-id="eb425-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="eb425-123">Microsoft. hisse. Canon. Applyifsıfırlaması a</span><span class="sxs-lookup"><span data-stu-id="eb425-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="eb425-124">Microsoft. hisse. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="eb425-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)