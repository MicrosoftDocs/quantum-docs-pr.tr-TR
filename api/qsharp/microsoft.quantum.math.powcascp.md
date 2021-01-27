---
uid: Microsoft.Quantum.Math.PowCAsCP
title: PowCAsCP işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowCAsCP
qsharp.summary: Internal. Since it is easiest to define the power of two complex numbers in cartesian form as returning in polar form, we define that here, then convert as needed.
ms.openlocfilehash: fb629f360e4b19715e406d4a4f4fae7a31e81736
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847065"
---
# <a name="powcascp-function"></a><span data-ttu-id="f7b6d-102">PowCAsCP işlevi</span><span class="sxs-lookup"><span data-stu-id="f7b6d-102">PowCAsCP function</span></span>

<span data-ttu-id="f7b6d-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f7b6d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7b6d-105">İç.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-105">Internal.</span></span> <span data-ttu-id="f7b6d-106">Kartezyen biçiminde iki karmaşık sayının gücünü, kutupsal biçimde döndürülen şekilde tanımlamak en kolay olduğundan, bunu burada tanımladık ve gerektiğinde dönüştürüyoruz.</span><span class="sxs-lookup"><span data-stu-id="f7b6d-106">Since it is easiest to define the power of two complex numbers in cartesian form as returning in polar form, we define that here, then convert as needed.</span></span>

```qsharp
function PowCAsCP (base_ : Microsoft.Quantum.Math.Complex, power : Microsoft.Quantum.Math.Complex) : Microsoft.Quantum.Math.ComplexPolar
```


## <a name="input"></a><span data-ttu-id="f7b6d-107">Giriş</span><span class="sxs-lookup"><span data-stu-id="f7b6d-107">Input</span></span>

### <a name="base_--complex"></a><span data-ttu-id="f7b6d-108">base_: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-108">base_ : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>




### <a name="power--complex"></a><span data-ttu-id="f7b6d-109">güç: [karmaşık](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-109">power : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>





## <a name="output--complexpolar"></a><span data-ttu-id="f7b6d-110">Çıkış: [Complexkutupsal](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="f7b6d-110">Output : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

