---
uid: Microsoft.Quantum.Canon.ApplyIf
title: Applyıf işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841880"
---
# <a name="applyif-operation"></a><span data-ttu-id="eb794-102">Applyıf işlemi</span><span class="sxs-lookup"><span data-stu-id="eb794-102">ApplyIf operation</span></span>

<span data-ttu-id="eb794-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb794-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb794-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb794-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb794-105">Klasik bir bit üzerine koşullu bir işlem uygular.</span><span class="sxs-lookup"><span data-stu-id="eb794-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="eb794-106">Description</span><span class="sxs-lookup"><span data-stu-id="eb794-106">Description</span></span>

<span data-ttu-id="eb794-107">Bir işlem `op` ve bir bit değeri verildiğinde, `bit` if ise için geçerlidir `op` `target` `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="eb794-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="eb794-108">Varsa, `false` hiçbir şey olmaz `target` .</span><span class="sxs-lookup"><span data-stu-id="eb794-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="eb794-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="eb794-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="eb794-110">Op: 'T => [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb794-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="eb794-111">Koşullu olarak uygulanacak bir işlem.</span><span class="sxs-lookup"><span data-stu-id="eb794-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="eb794-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eb794-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eb794-113">Op 'ın uygulanıp uygulanmadığını denetleyen bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="eb794-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="eb794-114">Hedef: 'T</span><span class="sxs-lookup"><span data-stu-id="eb794-114">target : 'T</span></span>

<span data-ttu-id="eb794-115">İşlemin uygulandığı giriş.</span><span class="sxs-lookup"><span data-stu-id="eb794-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb794-116">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb794-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eb794-117">Tür Parametreleri</span><span class="sxs-lookup"><span data-stu-id="eb794-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb794-118">Görüntülenemeyen</span><span class="sxs-lookup"><span data-stu-id="eb794-118">'T</span></span>

<span data-ttu-id="eb794-119">Koşullu olarak uygulanacak işlemin giriş türü.</span><span class="sxs-lookup"><span data-stu-id="eb794-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="eb794-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="eb794-120">Example</span></span>

<span data-ttu-id="eb794-121">Aşağıdaki, bir qubits kaydını bir değer dizisi olarak verilen bir klasik bit dizesiyle temsil eden bir hesaplama tabanlı duruma hazırlar `Bool` :</span><span class="sxs-lookup"><span data-stu-id="eb794-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="eb794-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="eb794-122">See Also</span></span>

- [<span data-ttu-id="eb794-123">Microsoft. hisse. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="eb794-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="eb794-124">Microsoft. hisse. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="eb794-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="eb794-125">Microsoft. hisse. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="eb794-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)