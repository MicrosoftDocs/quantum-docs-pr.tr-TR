---
uid: Microsoft.Quantum.Math.ModL
title: ModL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: f044ae16d93d31d0f28f5fcf076cff2bfef62eb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846831"
---
# <a name="modl-function"></a><span data-ttu-id="8b1e2-102">ModL işlevi</span><span class="sxs-lookup"><span data-stu-id="8b1e2-102">ModL function</span></span>

<span data-ttu-id="8b1e2-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8b1e2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8b1e2-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b1e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b1e2-105">Bir sayının başka bir sayıya göre mod sayısını döndürür.</span><span class="sxs-lookup"><span data-stu-id="8b1e2-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="8b1e2-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8b1e2-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="8b1e2-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8b1e2-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8b1e2-108">$A $, mod döndürülecek olan giriş.</span><span class="sxs-lookup"><span data-stu-id="8b1e2-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="8b1e2-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8b1e2-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8b1e2-110">$A $ 'in mod 'un döndürüleceği sayı.</span><span class="sxs-lookup"><span data-stu-id="8b1e2-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="8b1e2-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="8b1e2-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="8b1e2-112">Mod $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="8b1e2-112">The modulus $a \bmod b$.</span></span>