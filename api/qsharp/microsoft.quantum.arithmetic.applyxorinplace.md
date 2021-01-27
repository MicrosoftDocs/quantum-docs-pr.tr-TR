---
uid: Microsoft.Quantum.Arithmetic.ApplyXorInPlace
title: ApplyXorInPlace işlemi
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyXorInPlace
qsharp.summary: Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.
ms.openlocfilehash: 8f338d6638d554f3ead1f3c0e7b6605c7937abd8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843467"
---
# <a name="applyxorinplace-operation"></a><span data-ttu-id="1f70d-102">ApplyXorInPlace işlemi</span><span class="sxs-lookup"><span data-stu-id="1f70d-102">ApplyXorInPlace operation</span></span>

<span data-ttu-id="1f70d-103">Ad alanı: [Microsoft. hisse. aritmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="1f70d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="1f70d-104">Paket: [Microsoft. hisse. Standart](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f70d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f70d-105">Bir klasik tamsayı ile bir qubits yazmacı ile temsil edilen bir tamsayı arasında bit düzeyinde XOR işlemi uygular.</span><span class="sxs-lookup"><span data-stu-id="1f70d-105">Applies a bitwise-XOR operation between a classical integer and an integer represented by a register of qubits.</span></span>

```qsharp
operation ApplyXorInPlace (value : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="1f70d-106">Description</span><span class="sxs-lookup"><span data-stu-id="1f70d-106">Description</span></span>

<span data-ttu-id="1f70d-107">`X`Bir tamsayının 1 bite göre küçük endian kaydındaki işlemleri qubits 'e uygular.</span><span class="sxs-lookup"><span data-stu-id="1f70d-107">Applies `X` operations to qubits in a little-endian register based on 1 bits in an integer.</span></span>

<span data-ttu-id="1f70d-108">`value`Bir ' a göre belirlememize ve ' de bir işaretsiz tamsayı olmasına izin verin `target` , ardından `InPlaceXorLE` Şu eşleme tarafından verilen bir işlem gerçekleştirir: $ \ket{y}\rightarrow \ket{y\oplus a} $, burada $ \oplus $ bit DÜZEYINDE dışlamalı veya işleçtir.</span><span class="sxs-lookup"><span data-stu-id="1f70d-108">Let us denote `value` by a and let y be an unsigned integer encoded in `target`, then `InPlaceXorLE` performs an operation given by the following map: $\ket{y}\rightarrow \ket{y\oplus a}$ , where $\oplus$ is the bitwise exclusive OR operator.</span></span>

## <a name="input"></a><span data-ttu-id="1f70d-109">Giriş</span><span class="sxs-lookup"><span data-stu-id="1f70d-109">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="1f70d-110">değer: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f70d-110">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f70d-111">Negatif olmayan bir tamsayı.</span><span class="sxs-lookup"><span data-stu-id="1f70d-111">An integer which is assumed to be non-negative.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="1f70d-112">Hedef: [Litttaendian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1f70d-112">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1f70d-113">Küçük endian kodlamasıyla depolamak için kullanılan bir hisse kayıt `value` .</span><span class="sxs-lookup"><span data-stu-id="1f70d-113">A quantum register which is used to store `value` in little-endian encoding.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f70d-114">Çıkış: [birim](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f70d-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

