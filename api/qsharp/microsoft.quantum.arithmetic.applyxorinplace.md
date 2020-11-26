---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace işlemi
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: b7fc20ac421d5cff9baa3fe05450c1564f123505
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210123"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="7f3a4-102">ApplyXorInPlace işlemi</span><span class="sxs-lookup"><span data-stu-id="7f3a4-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="7f3a4-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7f3a4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7f3a4-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7f3a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7f3a4-105">Bir klasik tamsayı ile bir qubits yazmacı ile temsil edilen bir tamsayı arasında bit düzeyinde XOR işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="7f3a4-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7f3a4-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7f3a4-106">Description</span></span>

<span data-ttu-id="7f3a4-107">`X`Bir tamsayının 1 bite göre küçük endian kaydındaki işlemleri qubits 'e uygular.</span><span class="sxs-lookup"><span data-stu-id="7f3a4-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="7f3a4-108">`value`Bir ' a göre belirlememize ve ' de bir işaretsiz tamsayı olmasına izin verin `target` , ardından `InPlaceXorLE` Şu eşleme tarafından verilen bir işlem gerçekleştirir: $ \ket{y}\rightarrow \ket{y\oplus a} $, burada $ \oplus $ bit DÜZEYINDE dışlamalı veya işleçtir.</span><span class="sxs-lookup"><span data-stu-id="7f3a4-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="7f3a4-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="7f3a4-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="7f3a4-110">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f3a4-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7f3a4-111">Negatif olmayan bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="7f3a4-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="7f3a4-112">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7f3a4-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7f3a4-113">Küçük endian kodlamasıyla depolamak için kullanılan bir hisse kayıt `value` .</span><span class="sxs-lookup"><span data-stu-id="7f3a4-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7f3a4-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f3a4-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

