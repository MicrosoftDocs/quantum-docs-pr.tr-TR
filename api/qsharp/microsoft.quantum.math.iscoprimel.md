---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228143"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="53cf8-102">IsCoprimeL işlevi</span><span class="sxs-lookup"><span data-stu-id="53cf8-102">IsCoprimeL function</span></span>

<span data-ttu-id="53cf8-103">Ad alanı: [Microsoft. hisse. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="53cf8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="53cf8-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53cf8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53cf8-105">$A $ ve $b $ ortak ana ise true, aksi takdirde false döndürür.</span><span class="sxs-lookup"><span data-stu-id="53cf8-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="53cf8-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="53cf8-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="53cf8-107">y: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="53cf8-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="53cf8-108">ortak Prime 'nin test edilmekte olduğu ilk sayı</span><span class="sxs-lookup"><span data-stu-id="53cf8-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="53cf8-109">b: büyük [tamsayı](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="53cf8-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="53cf8-110">ortak Prime 'nin test edilmekte olan ikinci sayısı</span><span class="sxs-lookup"><span data-stu-id="53cf8-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="53cf8-111">Çıkış: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="53cf8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="53cf8-112">$A $ ve $b $ ortak asal ise true (ör. en büyük ortak bölen 1), aksi takdirde false</span><span class="sxs-lookup"><span data-stu-id="53cf8-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>