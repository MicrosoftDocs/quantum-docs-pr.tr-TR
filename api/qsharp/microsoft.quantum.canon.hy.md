---
uid: Microsoft.Quantum.Canon.HY
title: HY işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: ceca8eab8cb8f16333cd7a1e3c24e6cebe4ec8d7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206842"
---
# <a name="hy-operation"></a><span data-ttu-id="40a2d-102">HY işlemi</span><span class="sxs-lookup"><span data-stu-id="40a2d-102">HY operation</span></span>

<span data-ttu-id="40a2d-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="40a2d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="40a2d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="40a2d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="40a2d-105">Z ve Y eksenlerini karşılıklı olarak değiştiren Hadamard dönüşümüne Y tabanlı analog uygular.</span><span class="sxs-lookup"><span data-stu-id="40a2d-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="40a2d-106">Tek bir qubit üzerinde _Y = S H $ $H Y Hadamard dönüşümü:</span><span class="sxs-lookup"><span data-stu-id="40a2d-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="40a2d-107">\begin{hizalaması} H_Y \mathrel{: =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="40a2d-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="40a2d-108">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="40a2d-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="40a2d-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="40a2d-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="40a2d-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="40a2d-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="40a2d-111">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="40a2d-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40a2d-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40a2d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="40a2d-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="40a2d-113">See Also</span></span>

- [<span data-ttu-id="40a2d-114">Microsoft. hisse. Iç. H</span><span class="sxs-lookup"><span data-stu-id="40a2d-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)