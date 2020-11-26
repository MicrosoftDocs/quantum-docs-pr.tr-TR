---
uid: Microsoft.Quantum.Math.InverseModI
title: Evirsemodı işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195384"
---
# <a name="inversemodi-function"></a><span data-ttu-id="fd92e-102">Evirsemodı işlevi</span><span class="sxs-lookup"><span data-stu-id="fd92e-102">InverseModI function</span></span>

<span data-ttu-id="fd92e-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fd92e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fd92e-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd92e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd92e-105">$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi $b $ döndürür.</span><span class="sxs-lookup"><span data-stu-id="fd92e-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="fd92e-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="fd92e-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="fd92e-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd92e-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd92e-108">Ters çevrilen sayı</span><span class="sxs-lookup"><span data-stu-id="fd92e-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="fd92e-109">mod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd92e-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd92e-110">Sayıların tersine çevrilme olarak mod</span><span class="sxs-lookup"><span data-stu-id="fd92e-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="fd92e-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fd92e-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fd92e-112">$A \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $ gibi bir tamsayı $b $.</span><span class="sxs-lookup"><span data-stu-id="fd92e-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>