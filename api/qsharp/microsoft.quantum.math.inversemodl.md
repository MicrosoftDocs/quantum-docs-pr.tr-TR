---
uid: Microsoft.Quantum.Math.InverseModL
title: Evirsemodl işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733007"
---
# <a name="inversemodl-function"></a><span data-ttu-id="c8955-102">Evirsemodl işlevi</span><span class="sxs-lookup"><span data-stu-id="c8955-102">InverseModL function</span></span>

<span data-ttu-id="c8955-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c8955-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c8955-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c8955-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c8955-105">$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi $b $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="c8955-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="c8955-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="c8955-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c8955-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8955-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8955-108">Ters çevrilen sayı</span><span class="sxs-lookup"><span data-stu-id="c8955-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="c8955-109">mod: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8955-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8955-110">Sayıların tersine çevrilme olarak mod</span><span class="sxs-lookup"><span data-stu-id="c8955-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="c8955-111">Çıkış: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c8955-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c8955-112">$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi bir tamsayı $b $.</span><span class="sxs-lookup"><span data-stu-id="c8955-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>