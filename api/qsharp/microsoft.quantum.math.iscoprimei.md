---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 2c110f9abf18ee81bd72a68601d5c41ff756290a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851362"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="8beba-102">IsCoprimeI işlevi</span><span class="sxs-lookup"><span data-stu-id="8beba-102">IsCoprimeI function</span></span>

<span data-ttu-id="8beba-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="8beba-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="8beba-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8beba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8beba-105">$A $ ve $b $ ortak ana ise true, aksi takdirde false döndürür.</span><span class="sxs-lookup"><span data-stu-id="8beba-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="8beba-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8beba-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="8beba-107">y: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8beba-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8beba-108">ortak Prime 'nin test edilmekte olduğu ilk sayı</span><span class="sxs-lookup"><span data-stu-id="8beba-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="8beba-109">b: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8beba-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8beba-110">ortak Prime 'nin test edilmekte olan ikinci sayısı</span><span class="sxs-lookup"><span data-stu-id="8beba-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="8beba-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8beba-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8beba-112">$A $ ve $b $ ortak asal ise true (ör. en büyük ortak bölen 1), aksi takdirde false</span><span class="sxs-lookup"><span data-stu-id="8beba-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>