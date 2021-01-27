---
uid: Microsoft.Quantum.Canon.HY
title: HY işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: HY
qsharp.summary: >-
  Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.

  The Y Hadamard transformation $H_Y = S H$ on a single qubit is:

  \begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}. \end{align}
ms.openlocfilehash: 119d78c4cd8d5e5d92cb54ff652b082a1b99ae06
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840454"
---
# <a name="hy-operation"></a><span data-ttu-id="02a4b-102">HY işlemi</span><span class="sxs-lookup"><span data-stu-id="02a4b-102">HY operation</span></span>

<span data-ttu-id="02a4b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="02a4b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="02a4b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02a4b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02a4b-105">Z ve Y eksenlerini karşılıklı olarak değiştiren Hadamard dönüşümüne Y tabanlı analog uygular.</span><span class="sxs-lookup"><span data-stu-id="02a4b-105">Applies the Y-basis analog to the Hadamard transformation that interchanges the Z and Y axes.</span></span>

<span data-ttu-id="02a4b-106">Tek bir qubit üzerinde _Y = S H $ $H Y Hadamard dönüşümü:</span><span class="sxs-lookup"><span data-stu-id="02a4b-106">The Y Hadamard transformation $H_Y = S H$ on a single qubit is:</span></span>

<span data-ttu-id="02a4b-107">\begin{hizalaması} H_Y \mathrel{: =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ i &-i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="02a4b-107">\begin{align} H_Y \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ i & -i \end{bmatrix}.</span></span>
<span data-ttu-id="02a4b-108">\end{hizalaması}</span><span class="sxs-lookup"><span data-stu-id="02a4b-108">\end{align}</span></span>

```qsharp
operation HY (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="02a4b-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="02a4b-109">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="02a4b-110">Hedef: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="02a4b-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="02a4b-111">Gate 'in uygulanması gereken qubit.</span><span class="sxs-lookup"><span data-stu-id="02a4b-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="02a4b-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02a4b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="02a4b-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="02a4b-113">See Also</span></span>

- [<span data-ttu-id="02a4b-114">Microsoft. hisse. Iç. H</span><span class="sxs-lookup"><span data-stu-id="02a4b-114">Microsoft.Quantum.Intrinsic.H</span></span>](xref:Microsoft.Quantum.Intrinsic.H)