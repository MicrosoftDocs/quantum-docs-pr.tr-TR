---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Addı işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 9a90d15defd57cf2836a6fda5b52ddaa816fd55e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191032"
---
# <a name="addi-operation"></a><span data-ttu-id="1e4ba-102">Addı işlemi</span><span class="sxs-lookup"><span data-stu-id="1e4ba-102">AddI operation</span></span>

<span data-ttu-id="1e4ba-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1e4ba-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1e4ba-104">Paket: [Microsoft. hisse. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="1e4ba-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="1e4ba-105">Kayıt boyutuna bağlı olarak, birlikte taşıma ve olmadan ekleme arasında otomatik olarak seçer `ys` .</span><span class="sxs-lookup"><span data-stu-id="1e4ba-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1e4ba-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="1e4ba-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="1e4ba-107">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1e4ba-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1e4ba-108">$n $-bit adres.</span><span class="sxs-lookup"><span data-stu-id="1e4ba-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="1e4ba-109">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1e4ba-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1e4ba-110">En az $n $ qubits ile ADDEND.</span><span class="sxs-lookup"><span data-stu-id="1e4ba-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="1e4ba-111">Sonucu alacak.</span><span class="sxs-lookup"><span data-stu-id="1e4ba-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e4ba-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e4ba-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

