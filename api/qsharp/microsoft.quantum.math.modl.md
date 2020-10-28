---
uid: Microsoft.Quantum.Math.ModL
title: ModL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732706"
---
# <a name="modl-function"></a><span data-ttu-id="12ddb-102">ModL işlevi</span><span class="sxs-lookup"><span data-stu-id="12ddb-102">ModL function</span></span>

<span data-ttu-id="12ddb-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="12ddb-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="12ddb-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="12ddb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="12ddb-105">Bir sayının başka bir sayıya göre mod sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="12ddb-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="12ddb-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="12ddb-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="12ddb-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12ddb-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="12ddb-108">$A $, mod döndürülecek olan giriş.</span><span class="sxs-lookup"><span data-stu-id="12ddb-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="12ddb-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12ddb-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="12ddb-110">$A $ 'in mod 'un döndürüleceği sayı.</span><span class="sxs-lookup"><span data-stu-id="12ddb-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="12ddb-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="12ddb-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="12ddb-112">Mod $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="12ddb-112">The modulus $a \bmod b$.</span></span>