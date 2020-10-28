---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732850"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="2b522-102">IsCoprimeI işlevi</span><span class="sxs-lookup"><span data-stu-id="2b522-102">IsCoprimeI function</span></span>

<span data-ttu-id="2b522-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="2b522-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="2b522-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b522-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b522-105">$A $ ve $b $ ortak ana ise true, aksi takdirde false döndürür.</span><span class="sxs-lookup"><span data-stu-id="2b522-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="2b522-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="2b522-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="2b522-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b522-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b522-108">ortak Prime 'nin test edilmekte olduğu ilk sayı</span><span class="sxs-lookup"><span data-stu-id="2b522-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="2b522-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2b522-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2b522-110">ortak Prime 'nin test edilmekte olan ikinci sayısı</span><span class="sxs-lookup"><span data-stu-id="2b522-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="2b522-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2b522-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2b522-112">$A $ ve $b $ ortak asal ise true (ör. en büyük ortak bölen 1), aksi takdirde false</span><span class="sxs-lookup"><span data-stu-id="2b522-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>