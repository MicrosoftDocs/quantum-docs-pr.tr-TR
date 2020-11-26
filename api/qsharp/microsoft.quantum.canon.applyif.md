---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Applyıf işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c5a1012328fa012ee02707aa59c94ac9c44b8e87
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218844"
---
# <a name="applyif-operation"></a><span data-ttu-id="6bf2b-102">Applyıf işlemi</span><span class="sxs-lookup"><span data-stu-id="6bf2b-102">ApplyIf operation</span></span>

<span data-ttu-id="6bf2b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6bf2b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6bf2b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bf2b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bf2b-105">Klasik bir bit üzerine koşullu bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="6bf2b-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6bf2b-106">Description</span></span>

<span data-ttu-id="6bf2b-107">Bir işlem `op` ve bir bit değeri verildiğinde, `bit` if ise için geçerlidir `op` `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="6bf2b-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="6bf2b-108">Varsa, `false` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="6bf2b-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="6bf2b-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="6bf2b-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="6bf2b-110">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bf2b-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6bf2b-111">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="6bf2b-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6bf2b-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6bf2b-113">Op 'ın uygulanıp uygulanmadığını denetleyen bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="6bf2b-114">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="6bf2b-114">target : 'T</span></span>

<span data-ttu-id="6bf2b-115">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6bf2b-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6bf2b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6bf2b-117">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="6bf2b-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6bf2b-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="6bf2b-118">'T</span></span>

<span data-ttu-id="6bf2b-119">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bf2b-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6bf2b-120">See Also</span></span>

- [<span data-ttu-id="6bf2b-121">Microsoft. hisse. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="6bf2b-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="6bf2b-122">Microsoft. hisse. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="6bf2b-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="6bf2b-123">Microsoft. hisse. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="6bf2b-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)