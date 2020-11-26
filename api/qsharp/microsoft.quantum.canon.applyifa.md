---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218776"
---
# <a name="applyifa-operation"></a><span data-ttu-id="60b29-102">ApplyIfA işlemi</span><span class="sxs-lookup"><span data-stu-id="60b29-102">ApplyIfA operation</span></span>

<span data-ttu-id="60b29-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="60b29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="60b29-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60b29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60b29-105">Klasik bir bit üzerine koşullu bir adjointable işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="60b29-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="60b29-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="60b29-106">Description</span></span>

<span data-ttu-id="60b29-107">Bir işlem `op` ve bir bit değeri verildiğinde, `bit` if ise için geçerlidir `op` `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="60b29-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="60b29-108">Varsa, `false` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="60b29-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="60b29-109">Sonek, `A` uygulanacak işlemin adjointable olduğunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="60b29-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="60b29-110">Giriş</span><span class="sxs-lookup"><span data-stu-id="60b29-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="60b29-111">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)  sıfatı</span><span class="sxs-lookup"><span data-stu-id="60b29-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="60b29-112">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="60b29-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="60b29-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="60b29-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="60b29-114">Op 'ın uygulanıp uygulanmadığını denetleyen bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="60b29-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="60b29-115">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="60b29-115">target : 'T</span></span>

<span data-ttu-id="60b29-116">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="60b29-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60b29-117">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60b29-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="60b29-118">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="60b29-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60b29-119">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="60b29-119">'T</span></span>

<span data-ttu-id="60b29-120">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="60b29-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="60b29-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="60b29-121">See Also</span></span>

- [<span data-ttu-id="60b29-122">Microsoft. hisse. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="60b29-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="60b29-123">Microsoft. hisse. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="60b29-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="60b29-124">Microsoft. hisse. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="60b29-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)