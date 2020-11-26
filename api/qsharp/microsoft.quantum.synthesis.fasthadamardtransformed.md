---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Fasthadamarddönüştürüldü işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 3e48701f22ddf154721355866e15a85fca0bc7df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203102"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="0d840-102">Fasthadamarddönüştürüldü işlevi</span><span class="sxs-lookup"><span data-stu-id="0d840-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="0d840-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0d840-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0d840-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d840-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d840-105">{-1,1}Yates 'in yöntemi kullanılarak Kodlamadaki bir Boole Işlevinin Hadamard dönüşümünü hesaplar</span><span class="sxs-lookup"><span data-stu-id="0d840-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="0d840-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0d840-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="0d840-107">Func: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0d840-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0d840-108">Kodlamadaki Truth tablosu {-1,1}</span><span class="sxs-lookup"><span data-stu-id="0d840-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="0d840-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0d840-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0d840-110">İşlevin Spectral katsayısıdır</span><span class="sxs-lookup"><span data-stu-id="0d840-110">Spectral coefficients of the function</span></span>