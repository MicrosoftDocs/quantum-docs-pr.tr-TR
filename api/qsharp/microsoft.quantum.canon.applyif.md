---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Applyıf işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729599"
---
# <a name="applyif-operation"></a><span data-ttu-id="54c06-102">Applyıf işlemi</span><span class="sxs-lookup"><span data-stu-id="54c06-102">ApplyIf operation</span></span>

<span data-ttu-id="54c06-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="54c06-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="54c06-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54c06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54c06-105">Klasik bir bit üzerine koşullu bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="54c06-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="54c06-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="54c06-106">Description</span></span>

<span data-ttu-id="54c06-107">Bir işlem `op` ve bir bit değeri verildiğinde, `bit` if ise için geçerlidir `op` `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="54c06-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="54c06-108">Varsa, `false` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="54c06-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="54c06-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="54c06-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="54c06-110">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54c06-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="54c06-111">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="54c06-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="54c06-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="54c06-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="54c06-113">Op 'ın uygulanıp uygulanmadığını denetleyen bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="54c06-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="54c06-114">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="54c06-114">target : 'T</span></span>

<span data-ttu-id="54c06-115">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="54c06-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54c06-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54c06-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="54c06-117">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="54c06-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="54c06-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="54c06-118">'T</span></span>

<span data-ttu-id="54c06-119">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="54c06-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="54c06-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="54c06-120">See Also</span></span>

- [<span data-ttu-id="54c06-121">Microsoft. hisse. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="54c06-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="54c06-122">Microsoft. hisse. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="54c06-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="54c06-123">Microsoft. hisse. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="54c06-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)