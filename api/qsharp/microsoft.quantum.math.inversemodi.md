---
uid: Microsoft.Quantum.Math.InverseModI
title: Evirsemodı işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 6efc9da5f5ebb64065a90e749daa629dc2dce9cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733010"
---
# <a name="inversemodi-function"></a><span data-ttu-id="0a7ba-102">Evirsemodı işlevi</span><span class="sxs-lookup"><span data-stu-id="0a7ba-102">InverseModI function</span></span>

<span data-ttu-id="0a7ba-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0a7ba-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0a7ba-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0a7ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0a7ba-105">$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi $b $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="0a7ba-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="0a7ba-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="0a7ba-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="0a7ba-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a7ba-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0a7ba-108">Ters çevrilen sayı</span><span class="sxs-lookup"><span data-stu-id="0a7ba-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="0a7ba-109">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a7ba-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0a7ba-110">Sayıların tersine çevrilme olarak mod</span><span class="sxs-lookup"><span data-stu-id="0a7ba-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="0a7ba-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0a7ba-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0a7ba-112">$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi bir tamsayı $b $.</span><span class="sxs-lookup"><span data-stu-id="0a7ba-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>