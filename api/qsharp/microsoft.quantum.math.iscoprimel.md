---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL işlevi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851338"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="4eca3-102">IsCoprimeL işlevi</span><span class="sxs-lookup"><span data-stu-id="4eca3-102">IsCoprimeL function</span></span>

<span data-ttu-id="4eca3-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4eca3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4eca3-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4eca3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4eca3-105">$A $ ve $b $ ortak ana ise true, aksi takdirde false döndürür.</span><span class="sxs-lookup"><span data-stu-id="4eca3-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="4eca3-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="4eca3-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="4eca3-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4eca3-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4eca3-108">ortak Prime 'nin test edilmekte olduğu ilk sayı</span><span class="sxs-lookup"><span data-stu-id="4eca3-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="4eca3-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="4eca3-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="4eca3-110">ortak Prime 'nin test edilmekte olan ikinci sayısı</span><span class="sxs-lookup"><span data-stu-id="4eca3-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="4eca3-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4eca3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4eca3-112">$A $ ve $b $ ortak asal ise true (ör. en büyük ortak bölen 1), aksi takdirde false</span><span class="sxs-lookup"><span data-stu-id="4eca3-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>