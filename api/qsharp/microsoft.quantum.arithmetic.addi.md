---
uid: Microsoft.Quantum.Arithmetic.AddI
title: Addı işlemi
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddI
qsharp.summary: Automatically chooses between addition with carry and without, depending on the register size of `ys`.
ms.openlocfilehash: 7ee2b9099ea65b95647422dadc1efe4bf043d147
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731895"
---
# <a name="addi-operation"></a><span data-ttu-id="8de70-102">Addı işlemi</span><span class="sxs-lookup"><span data-stu-id="8de70-102">AddI operation</span></span>

<span data-ttu-id="8de70-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8de70-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8de70-104">Leyebilir [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8de70-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8de70-105">Kayıt boyutuna bağlı olarak, birlikte taşıma ve olmadan ekleme arasında otomatik olarak seçer `ys` .</span><span class="sxs-lookup"><span data-stu-id="8de70-105">Automatically chooses between addition with carry and without, depending on the register size of `ys`.</span></span>

```qsharp
operation AddI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="8de70-106">Giriş</span><span class="sxs-lookup"><span data-stu-id="8de70-106">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="8de70-107">xs: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8de70-107">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8de70-108">$n $-bit adres.</span><span class="sxs-lookup"><span data-stu-id="8de70-108">$n$-bit addend.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="8de70-109">YS: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8de70-109">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8de70-110">En az $n $ qubits ile ADDEND.</span><span class="sxs-lookup"><span data-stu-id="8de70-110">Addend with at least $n$ qubits.</span></span> <span data-ttu-id="8de70-111">Sonucu alacak.</span><span class="sxs-lookup"><span data-stu-id="8de70-111">Will hold the result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8de70-112">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8de70-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

