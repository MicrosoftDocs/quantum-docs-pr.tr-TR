---
uid: Microsoft.Quantum.Canon.Angle
title: Açılı işlevi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219422"
---
# <a name="angle-function"></a><span data-ttu-id="d252b-102">Açılı işlevi</span><span class="sxs-lookup"><span data-stu-id="d252b-102">Angle function</span></span>

<span data-ttu-id="d252b-103">Ad alanı: [Microsoft. hisse. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d252b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d252b-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d252b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d252b-105">`index`Tek sayıda 1s ve-1, çift sayıda 1s varsa 1 değerini döndürür `index` .</span><span class="sxs-lookup"><span data-stu-id="d252b-105">Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.</span></span>

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a><span data-ttu-id="d252b-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d252b-106">Description</span></span>

<span data-ttu-id="d252b-107">Değer, döndürme açısını belirleyen belirli bir atama için n değişkeninin ve işlevinin Rademacher-Walsh tayfının işaretine karşılık gelir.</span><span class="sxs-lookup"><span data-stu-id="d252b-107">Value corresponds to the sign of the coefficient of the Rademacher-Walsh spectrum of the n-variable AND function for a given assignment that decides the angle of the rotation.</span></span>

## <a name="input"></a><span data-ttu-id="d252b-108">Giriş</span><span class="sxs-lookup"><span data-stu-id="d252b-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="d252b-109">Dizin: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d252b-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d252b-110">Tamsayı olarak giriş ataması (0 ile 2 ^ n-1 arasında)</span><span class="sxs-lookup"><span data-stu-id="d252b-110">Input assignment as integer (from 0 to 2^n - 1)</span></span>



## <a name="output--int"></a><span data-ttu-id="d252b-111">Çıkış: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d252b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

