---
uid: Microsoft.Quantum.Arithmetic.CompareGTI
title: Comparegtı işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTI
qsharp.summary: 'Wrapper for integer comparison: `result = x > y`.'
ms.openlocfilehash: b6e82eb7e9c068eff5bb320bb797a8fb0f8f921b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223485"
---
# <a name="comparegti-operation"></a><span data-ttu-id="45b61-102">Comparegtı işlemi</span><span class="sxs-lookup"><span data-stu-id="45b61-102">CompareGTI operation</span></span>

<span data-ttu-id="45b61-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="45b61-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="45b61-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="45b61-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="45b61-105">Tamsayı karşılaştırması için sarmalayıcı: `result = x > y` .</span><span class="sxs-lookup"><span data-stu-id="45b61-105">Wrapper for integer comparison: `result = x > y`.</span></span>

```qsharp
operation CompareGTI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="45b61-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="45b61-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="45b61-107">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45b61-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="45b61-108">İlk $n $-bit numarası</span><span class="sxs-lookup"><span data-stu-id="45b61-108">First $n$-bit number</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="45b61-109">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="45b61-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="45b61-110">İkinci $n $-bit numarası</span><span class="sxs-lookup"><span data-stu-id="45b61-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="45b61-111">Sonuç: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="45b61-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="45b61-112">$X > y $ olarak çevrilmiş</span><span class="sxs-lookup"><span data-stu-id="45b61-112">Will be flipped if $x > y$</span></span>



## <a name="output--unit"></a><span data-ttu-id="45b61-113">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="45b61-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

