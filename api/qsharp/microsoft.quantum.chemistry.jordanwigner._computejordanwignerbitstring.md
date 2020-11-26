---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 8121421a77174ef3e894381b281964b448e00a18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203952"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="6cab2-102">_ComputeJordanWignerBitString işlevi</span><span class="sxs-lookup"><span data-stu-id="6cab2-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="6cab2-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="6cab2-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="6cab2-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6cab2-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6cab2-105">Bir fermıonic işlecinde, çift sayıda oluşturma/himaılasyon işleçlerine sahip fermıon dizinleri arasında Ürdün Mııner dizesinin Z bileşenini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="6cab2-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="6cab2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="6cab2-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="6cab2-107">nFermions: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6cab2-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6cab2-108">Sistemdeki fermıons sayısı.</span><span class="sxs-lookup"><span data-stu-id="6cab2-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="6cab2-109">ıdxfermions: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6cab2-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6cab2-110">fermıonic işleç dizinleri.</span><span class="sxs-lookup"><span data-stu-id="6cab2-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6cab2-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="6cab2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="6cab2-112">Uygulanacağı bit dizesi `Bool[]` `true` `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="6cab2-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>