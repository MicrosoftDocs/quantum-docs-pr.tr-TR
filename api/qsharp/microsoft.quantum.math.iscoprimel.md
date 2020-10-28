---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL işlevi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732250"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="4526a-102">IsCoprimeL işlevi</span><span class="sxs-lookup"><span data-stu-id="4526a-102">IsCoprimeL function</span></span>

<span data-ttu-id="4526a-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4526a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4526a-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4526a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4526a-105">$A $ ve $b $ ortak ana ise true, aksi takdirde false döndürür.</span><span class="sxs-lookup"><span data-stu-id="4526a-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4526a-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4526a-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4526a-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4526a-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4526a-108">ortak Prime 'nin test edilmekte olduğu ilk sayı</span><span class="sxs-lookup"><span data-stu-id="4526a-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4526a-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4526a-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4526a-110">ortak Prime 'nin test edilmekte olan ikinci sayısı</span><span class="sxs-lookup"><span data-stu-id="4526a-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="4526a-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4526a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4526a-112">$A $ ve $b $ ortak asal ise true (ör. en büyük ortak bölen 1), aksi takdirde false</span><span class="sxs-lookup"><span data-stu-id="4526a-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>