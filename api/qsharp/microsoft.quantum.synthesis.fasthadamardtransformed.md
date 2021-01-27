---
uid: Microsoft.Quantum.Synthesis.FastHadamardTransformed
title: Fasthadamarddönüştürüldü işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FastHadamardTransformed
qsharp.summary: Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method
ms.openlocfilehash: be54413ef2d3fdaf7ddc726bc0906adb4ec382ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855463"
---
# <a name="fasthadamardtransformed-function"></a><span data-ttu-id="63b58-102">Fasthadamarddönüştürüldü işlevi</span><span class="sxs-lookup"><span data-stu-id="63b58-102">FastHadamardTransformed function</span></span>

<span data-ttu-id="63b58-103">Ad alanı: [Microsoft. hisse. sensıs](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="63b58-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="63b58-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63b58-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63b58-105">{-1,1}Yates 'in yöntemi kullanılarak Kodlamadaki bir Boole Işlevinin Hadamard dönüşümünü hesaplar</span><span class="sxs-lookup"><span data-stu-id="63b58-105">Computes Hadamard transform of a Boolean function in {-1,1} encoding using Yates's method</span></span>

```qsharp
function FastHadamardTransformed (func : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="63b58-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="63b58-106">Input</span></span>

### <a name="func--int"></a><span data-ttu-id="63b58-107">Func: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="63b58-107">func : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="63b58-108">Kodlamadaki Truth tablosu {-1,1}</span><span class="sxs-lookup"><span data-stu-id="63b58-108">Truth table in {-1,1} encoding</span></span>



## <a name="output--int"></a><span data-ttu-id="63b58-109">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="63b58-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="63b58-110">İşlevin Spectral katsayısıdır</span><span class="sxs-lookup"><span data-stu-id="63b58-110">Spectral coefficients of the function</span></span>

## <a name="example"></a><span data-ttu-id="63b58-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="63b58-111">Example</span></span>

```qsharp
FastHadamardTransformed([1, 1, 1, -1]); // [2, 2, 2, -2]
```