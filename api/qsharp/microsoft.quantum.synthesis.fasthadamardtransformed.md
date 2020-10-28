---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Fasthadamarddönüştürüldü işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: 2b84e92d08a3baad2552780cae91f447830cac82
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733895"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="0605e-102">Fasthadamarddönüştürüldü işlevi</span><span class="sxs-lookup"><span data-stu-id="0605e-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="0605e-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="0605e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="0605e-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0605e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0605e-105">{-1,1}Yates 'in yöntemi kullanılarak Kodlamadaki bir Boole Işlevinin Hadamard dönüşümünü hesaplar</span><span class="sxs-lookup"><span data-stu-id="0605e-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="0605e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0605e-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="0605e-107">Func: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0605e-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0605e-108">Kodlamadaki Truth tablosu {-1,1}</span><span class="sxs-lookup"><span data-stu-id="0605e-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="0605e-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0605e-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0605e-110">İşlevin Spectral katsayısıdır</span><span class="sxs-lookup"><span data-stu-id="0605e-110">Spectral coefficients of the function</span></span>