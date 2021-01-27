---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ComputeJordanWignerBitString
title: _ComputeJordanWignerBitString işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ComputeJordanWignerBitString
qsharp.summary: Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.
ms.openlocfilehash: 82b5e433f79c93c640b89e6365e5f468bacd892e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839521"
---
# <a name="_computejordanwignerbitstring-function"></a><span data-ttu-id="0948c-102">_ComputeJordanWignerBitString işlevi</span><span class="sxs-lookup"><span data-stu-id="0948c-102">_ComputeJordanWignerBitString function</span></span>

<span data-ttu-id="0948c-103">Ad alanı: [Microsoft. hisse. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="0948c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="0948c-104">Paket: [Microsoft. hisse. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0948c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="0948c-105">Bir fermıonic işlecinde, çift sayıda oluşturma/himaılasyon işleçlerine sahip fermıon dizinleri arasında Ürdün Mııner dizesinin Z bileşenini hesaplar.</span><span class="sxs-lookup"><span data-stu-id="0948c-105">Computes Z component of Jordan–Wigner string between fermion indices in a fermionic operator with an even number of creation / annihilation operators.</span></span>

```qsharp
function _ComputeJordanWignerBitString (nFermions : Int, idxFermions : Int[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="0948c-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0948c-106">Input</span></span>

### <a name="nfermions--int"></a><span data-ttu-id="0948c-107">nFermions: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0948c-107">nFermions : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0948c-108">Sistemdeki fermıons sayısı.</span><span class="sxs-lookup"><span data-stu-id="0948c-108">The Number of fermions in the system.</span></span>


### <a name="idxfermions--int"></a><span data-ttu-id="0948c-109">ıdxfermions: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0948c-109">idxFermions : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0948c-110">fermıonic işleç dizinleri.</span><span class="sxs-lookup"><span data-stu-id="0948c-110">fermionic operator indices.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0948c-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="0948c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="0948c-112">Uygulanacağı bit dizesi `Bool[]` `true` `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="0948c-112">Bitstring `Bool[]` that is `true` where a `PauliZ` should be applied.</span></span>

## <a name="example"></a><span data-ttu-id="0948c-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="0948c-113">Example</span></span>

<span data-ttu-id="0948c-114">Let bitString = _ComputeJordanWignerBitString (6, [0, 1, 2, 6]); bitString [false, false, false, true, true, true, false].</span><span class="sxs-lookup"><span data-stu-id="0948c-114">let bitString = _ComputeJordanWignerBitString(6, [0,1,2,6]) ; // bitString is [false, false, false ,true, true, true, false].</span></span>