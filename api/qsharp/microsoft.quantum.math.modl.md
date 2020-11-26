---
uid: Microsoft.Quantum.Math.ModL
title: ModL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 0b1ac69cc1474e9cfa6a3489b2b2fdf497e812e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227803"
---
# <a name="modl-function"></a><span data-ttu-id="62c23-102">ModL işlevi</span><span class="sxs-lookup"><span data-stu-id="62c23-102">ModL function</span></span>

<span data-ttu-id="62c23-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="62c23-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="62c23-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62c23-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62c23-105">Bir sayının başka bir sayıya göre mod sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="62c23-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="62c23-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="62c23-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="62c23-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="62c23-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="62c23-108">$A $, mod döndürülecek olan giriş.</span><span class="sxs-lookup"><span data-stu-id="62c23-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="62c23-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="62c23-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="62c23-110">$A $ 'in mod 'un döndürüleceği sayı.</span><span class="sxs-lookup"><span data-stu-id="62c23-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="62c23-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="62c23-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="62c23-112">Mod $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="62c23-112">The modulus $a \bmod b$.</span></span>